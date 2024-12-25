[![Actions Status](https://github.com/raku-community-modules/Statistics-LinearRegression/actions/workflows/linux.yml/badge.svg)](https://github.com/raku-community-modules/Statistics-LinearRegression/actions) [![Actions Status](https://github.com/raku-community-modules/Statistics-LinearRegression/actions/workflows/macos.yml/badge.svg)](https://github.com/raku-community-modules/Statistics-LinearRegression/actions) [![Actions Status](https://github.com/raku-community-modules/Statistics-LinearRegression/actions/workflows/windows.yml/badge.svg)](https://github.com/raku-community-modules/Statistics-LinearRegression/actions)

NAME
====

Statistics::LinearRegression - simple linear regression

SYNOPSIS
========

Gather some data

```raku
my @arguments = 1,2,3;
my @values = 3,2,1;
```

Build model and predict value for some x using object

```raku
use Statistics::LinearRegression;
my $x = 15;
my $y = my LR.new(@arguments, @values).at($x);
```

If you prefer bare functions, use :ALL

```raku
use Statistics::LinearRegression :ALL;
my ($slope, $intercept) = get-parameters(@arguments, @values);
my $x = 15;
my $y = value-at($x, $slope, $intercept);
```

DESCRIPTION
===========

LinearRegression finds slope and intercept parameters of linear function by minimizing mean square error.

Value at y is calculated using `y = slope × x + intercept`.

TODO
====

  * R^2 and p-value calculation 

  * support for other objective functions

CHANGES
=======

  * 1.1.0 LR class exported by default, bare subroutines need :ALL

AUTHOR
======

Paweł Szulc

COPYRIGHT AND LICENSE
=====================

Copyright 2016 -2017 Paweł Szulc

Copyright 2024 Raku Community

This library is free software; you can redistribute it and/or modify it under the Artistic License 2.0.

