# variable
replcement of :root

              $veriable-name: value;
Declare  -->  $color-primary: cyan;
              $font-size: 5em;

use      --> .selector {background: $color-primary}








# Partials : _fileName.scss        for diff part of code
and use it    @import 'fileName'

Order matters while importing

different file for different type of use case, like;
1. variables [variables, function]
2. base [base & layout[grid, flex]]
3. colors
4. Components [button, card, navbar]
5. Utilities [margin, padding, opacity]









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











# maps
maps are like objects in js
You can add, delete, manipulate in the map value

$font-weight: (
    "regular": 400,
    "medium": 600,
    "bold": 900
);semicolumn is important

1. Get the map value
map-get(map-name, key);
map-get($font-weight, "regular");

2. checking the map has that key
map-has-key(map-name, key) // If key is availble: true, flase

3. Removing map key
map-remove(map-name, key) // key, that you want to delete

4. Mergin two values
map-merge(map-name, ("key", vlaue))







# Lists
$variable: value1, value2, value3, value4, value5;
- and can loop over it







# Functions
Function should use for calculate value & return vlaue;

@function funcName($para-name) {
    @return anything you want to use
}

use it like

propertyName: funcName(para-value)


build-in function lighten()














# mixin
little bit similar to the function
But mixin should be use for define style

1. It use for repetative code
2. Switching between theme
3. media Query

@mixin name($para: defaultValue) {
    display: flex;
    align-item: center;
    flex-direction: $para;
}

.className1: {@include name(row)}
.className2: {@include name(column)}
.className2: {@include name} --> It's gonna take default value


Best use case of @mixin is switching between light-dark mode






# Conditionals
@if ($booleanValue and $anotherBooleanValue) {

} @else {

}




# @content;




# @extend className;
A bit similler to the mixin, but it dosen't take argument
and in our main css file it convert it in (,) seprated clasName: .class1, .class2

@extend .clasName; inherites all the property from the given clasName

and if you don't want to create extra className use (%) instead of (.)

%className
.class1 {all the propery}

.class2 {
    @extend .class1;
    @exted %className;

    class2 style
}











# Math Operations
Sass has a handful of standard math operators
@use 'sass:math'

like +, -, *, math.div(), and %.


1. substract
40% - 12%        --  right
40% - 20px       --  wrong


2. division
math.div(value, 5)  --> vlaue/5


@debug "value you want to print"
@debug math.floor(3.7)











# Loops
@each $key, $val in $map-name {
    .text-#{$key} {
        color: $val;
    }
}


@for $i from 1 through 9 {
    .text-#{$key}-light-#{$i} {
        color: mix(white, $val, $i * 10);
    }
}

* Applications
1. loop through the map and create classes based on the key




# Custom Utilities Classes





# How to use this CSS library in the future project, and customize
how to change the variables, 

so ya, first of all create a seprate scss/index.scss file
connect it to the html file

and in this your scss file, @import libray
and in your library the variable value you want to change use !default;

like: $variable: vlaue !default;

make changes before @import main;
