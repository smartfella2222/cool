# IDK ADMIN

Hope somebody else hasn't taken this name..
this is my open source admin, change all you need! :)

*I'll update this sometimes, and maybe add some more customization via the admin and source*

**loadstring**
``` lua
loadstring(game:HttpGet('https://raw.githubusercontent.com/smartfella2222/cool/refs/heads/main/main'))()
```

## Source Customization


#### Commands
If you would like to add a command, heres the template:
```lua
function testcmd()
  print('command ran!')
end
cmds[testcmd] = { --Make sure the insides of "cmds" is the command function
  ['Name'] = {"test1", "test2"}, --Commands can have multiple names, specifically for abbreviations.
  ['CommandStyle'] = 2, --Icon for the script, 1 = GUI, 2 = Script, 3 = Break script; e.g. unfly
  ['Description'] = 'This is a cool test command!',
  ['Args'] = {}, --MORE ON ARGUMENTS BELOW IF YOU NEED INSIGHT ON THEM
  ['Command'] = testcmd --Make sure this is the command function!
}
```

you should put this somewhere where all the other commands are located in the script.

#### Arguments
The max amount of arguments in a command can **ONLY BE THREE**, this limitation is in place to prevent arguments from going off
the screen and off the command suggestion box, If more then three are added, the args after the third one wont work. 
Its also recommended that your arg names are short, so they can fit in the suggestion box.

If your command doesn't need any arguments, you can easily do:
```lua
['Args'] = {},
```

And if you need to add arguments, you can do:
```lua
['Args'] = {
    'arg1',
    'arg2',
    'arg3' --You can only do 3!
},
```

The "Args" table is only for showing up in the inferface and working in the command box, when you need to embed those args in the command, you simply have to add them in the command function.
so a complete argument command would look something like this:

```lua
function testcmd(arg, arg2) -- two args for the command
  print(arg)
  print(arg2)
end
cmds[testcmd] = {
  ['Name'] = "testcmd",
  ['CommandStyle'] = 2,
  ['Description'] = 'This is a cool test command!',
  ['Args'] = {
      'arg1',
      'arg2' -- relating two args needed here
  },
  ['Command'] = testcmd
}
```

#### Notifications
If you would like to add a notification in your script, you can do so via the admin_notify function.
```lua
admin_notify('Title', "Description", 5 --[[This is the length of the notification.]])
```

Make sure all arguments are specified or else the notification won't work.
