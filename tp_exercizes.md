Exercizes
=========

Class 1
-------

### Exercize 1 [arrays]

Write the body of the following `Invert` function:

```ada
function Invert (S : String) return String
   ...
begin
   ...
end Invert;
```

`Invert` shall return the inverted string, with the same bounds as `S`.

You can put this function inside a main procedure that will serve as a test procedure:

```ada
--  test_invert.adb
with Invert;
with Ada.Text_IO; use Ada.Text_IO;

procedure Test_Invert is
   function Invert (S : String) return String
      ...
   begin
      ...
   end Invert;
begin
  ...  --  Put some tests here
end Test_Invert;
```

### Exercize 1b [arrays]

Write the same subprogram, but as a procedure, that inverts the string in-place:

```ada
procedure Invert (S : in out String)
   ...
begin
   ...
end Invert;
```

Write associated tests.

### Exercize 2 [arrays]

Write a function that converts an `Integer` into a `String`, without using the
`'Image` attribute. Start by handling positive integers, then transition to all
integers.

Write associated tests.

### Exercize 3 [arrays]

Write a function that converts a `String` into an `Integer`, with associated
tests.

### BONUS Exercize 4 [arrays]

Write a function that converts an `Integer` into a `String` using
[Roman numerals](https://en.wikipedia.org/wiki/Roman_numerals).

Write the inverse function.
