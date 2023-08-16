# variable
replcement of :root

declare  -->  $color-primary: cyan;
use --> .selector {background: $color-primary}







# maps
maps are like objects in js

$font-weight: (
    "regular": 400,
    "medium": 600,
    "bold": 900
); semicolmn is important

* how to use this
font-weight: map-get($map: font-weight, $key: regular);









# Nesting
.className {
    p {
        something: something;
    }


    &__second {                      & --> .className__second{}
        something: something;
    }


    Interpulation
    #{&}__second {                    #{&} --> .className .className__second{}
        something: something;
    }
}










# Partials : _fileName.scss        for diff part of code
and use it    @import 'fileName'









# Functions
Function should use for calculate value, return vlaue;

@function funcName($para-name) {
    @return anything you want to use
}

use it like

propertyName: funcName(para-value)

















# mixin
little bit similar to the function
But mixin should be use for define style

It use for repetative code

@mixin name($para) {
    display: flex;
    align-item: center;
    flex-direction: $para;
}

.className1: {@include name(row)}
.className2: {@include name(column)}


Best use case of @mixin is switching between light-dark mode





















# @if $booleanValue{}