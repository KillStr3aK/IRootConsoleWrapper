# IRootConsoleWrapper
Wrapper for SourceMod extensions to create IRootConsole menu and commands in an easy way

```cpp
#include "ConsoleMenu.h"

class Menu : public ConsoleMenu
{
public:
    Menu(const char* name) : ConsoleMenu(name)
    {
        ConsoleMenuCategory* category = this->RegisterMenuCategory("mycategory", "description for this category");

        category->RegisterCommand("test", "This is a test command", [](ConsoleMenuCommand* command, const ICommandArgs* args)
        {
            rootconsole->ConsolePrint("[%s] Not implemented %s", SMEXT_CONF_LOGTAG, command->GetName());
        });
    }
};
```
