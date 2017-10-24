---
layout: post
title: The & Operator in Elixir
comments: true
author: komlanvi
description: Tutorial on the utility of the Elixir & operator and why and how to use it.
permalink: /the-&-operator-in-elixir/
---

Writing short helpers functions in Elixir is a natural behavior since Elixir is a functional
programming language and thankfully Elixir provides a shortcut to save us time: The & operator.  
<!-- more -->

### Create shortcut anonymous functions

Before we get some explanations let's see what it looks like writing shortcuts anonymous functions.

``` elixir
fn x -> x + 1 end is same as &(&1 + 1)
fn x -> x + x end is same as &(&1 + &1)
fn x, y -> x + y end is same as &(&1 + &2)
```

Now what happens is that the `&` operator converts the expression inside the parentheses into an anonymous
function where &1, &2 and so on correspond to the parameters given to the function. So `&(IO.puts &1 <> " " <> &2)` is equivalent to `fn hello, world -> IO.puts hello <> " " <> world end.`
Look at the length of each version and judge by yourself.

A particular use case where the & operator is useful is when we have to pass a function to another function (a common task in Elixir when dealing with data structures).

For example, we want to get each atom from the following list `[19, :elixir, 77, :phoenix, 64, {:one, "one"}, :erlang]` returned as a string.

``` elixir
list = [19, :elixir, 77, :phoenix, 64, {:one, "one"}, :erlang]
list
 |> Enum.filter(&(is_atom(&1)))
 |> Enum.map(&(to_string(&1)))
```

When run, the above code outputs: `["elixir", "phoenix", "erlang"]` which is exactly what we expected.

### Capture named function

Another feature of the `&` operator is to capture named functions.
Capturing mean `&` can turn a named function into an anonymous function.  
The above example could be then refactored capturing `is_atom` and `to_string` as following:

``` elixir
list = [19, :elixir, 77, :phoenix, 64, {:one, "one"}, :erlang]
list
  |> Enum.filter(&is_atom/1)
  |> Enum.map(&to_string/1)
```

And the output remains the same.  
This is an optimization since instead of creating an anonymous function and allocating new memory, Elixir
maintains a direct reference to the original function.
Hope you'll find this helpful and now that you get it go and save your precious time.
