---
tags:
    - tlo
---
# `Bool`

Creates a bool object from a string. The resulting value is a _bool_ depending on whether the given string is falsey or not.

"Falsey" is defined as any of the following values:

* Empty String
* FALSE
* NULL
* The string "0"

If the string is one of these values, the resulting bool is `false`. Otherwise, it is `true`.

## Forms

### {{ renderMember(type='bool', name='Bool', params='Text') }}

:   Converts the given _Text_ to a bool based on the rules presented above.


## Usage

=== "MQScript"

    ```
    /declare MyVar bool
    /varset MyVar ${Bool[This is true]}

    | prints TRUE
    /echo ${MyVar}

    /varset MyVar ${Bool[NULL]}

    | prints FALSE
    /echo ${MyVar}
    ```

=== "Lua"

    ```lua
    local myVar

    -- prints true
    myVar = mq.TLO.Bool('This is true')()
    print(myVar)

    -- prints false
    myVar = mq.TLO.Bool('NULL')()
    print(myVar)
    ```

[bool]: ../data-types/datatype-bool.md