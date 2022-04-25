# Operation API

Operation API mostly responsible for those peripheral methods, that are somehow influence surrounding worlds. Most of these operations will have cooldowns - so you can't call them without delay. Also, some operation with long cooldowns we have it at each turtle start or upgrade equipment, so take this in account.

You can configure cooldowns in the configuration file. Also, threshold for initial cooldown also can be configured via `initialCooldownSensetiveLevel` or even disabled with `isInitialCooldownEnabled` settings key.

| Function                           | Returns                 | Description                                    |
|------------------------------------|-------------------------|------------------------------------------------|
| getCooldown(operationName: string) | number                  | Returns times in milliseconds of left cooldown |
| getOperations()                    | table (list of strings) | Returns all available operations               |
