
#API

## TextboxService

### Constructors

#### createGroup()

``` lua title="<span style='color: grey; font-size: 13px;'>Example Code</span>"
local Group = TextboxService.createGroup(name)
```
Constructs an empty customizable Group.

!!! warning 
    You cannot use **duplicate names.** This will throw error message if you try to use duplicated names.

#### new()

```lua title="<span style='color: grey; font-size: 13px;'>Example Code</span>"
local Textbox = TextboxService.new()
```
Constructs an empty Textbox instance.

#### insert()

``` lua title="<span style='color: grey; font-size: 13px;'>Example Code</span>"
TextboxService.insert(Group, Textbox)
```
Insert a Textbox into a given Group or name of Group.

!!! info "Examples"
    === "Instance"
        ``` lua
        local Group1 = TextboxService.createGroup("Group1")
        local Textbox = TextboxService.new()
    
        TextboxService.insert(Group1, Textbox)
        ```
    === "Name"
        ``` lua
        local Group1 = TextboxService.createGroup("Group1")
        local Textbox = TextboxService.new()
    
        TextboxService.insert(Group1, Textbox)
        ```

### Group Methods



### Textbox Methods

#### lock()

```lua title="<span style='color: grey; font-size: 13px;'>Example Code</span>"
Textbox:lock()
```
Prevent Textbox from properity changes from Group. </br>
#### unlock()

```lua title="<span style='color: grey; font-size: 13px;'>Example Code</span>"
Textbox:unlock()
```
Disable the locked state of Textbox.

#### filter()

```lua title="<span style='color: grey; font-size: 13px;'>Example Code</span>"
Textbox:filter(Async)
```
Filter the texts of the Textbox with given string of Sync type.
!!! info "Asyncs"
    * **NonChat** = GetNonChatStringForUserAsync()
    * **Chat** = GetChatStringForUserAsync()
    * **Broadcast** = GetBroadcastStringAsync()

#### modify()

```lua title="<span style='color: grey; font-size: 13px;'>Example Code</span>"
Textbox:modify(properity, value)
```
Modify the properity with given value.

### Properties

#### TextLimit

```lua title="<span style='color: grey; font-size: 13px;'>Example Code</span>"
Textbox:modify("TextLimit", number)
```
Limit the text length of the Textbox.</br>
Activates **LimitReached** event once if text has reached the limit.

!!! note
    This property is not proper for **multi-line** Textbox.</br>
    **Multi-line** Textboxes are great with [**LineLimit**](#){} not a **TextLimit** alone.
    
#### LineLimit