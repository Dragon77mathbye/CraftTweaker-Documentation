# Команды

Вы можете использовать этот класс для отправки команды, вы не можете использовать этот класс для создания новых команд! Посмотрите на [CommandEvent](/Vanilla/Events/Events/CommandEvent/) , чтобы добавить новые команды. Вы также можете использовать [ICommandManager](/Vanilla/Commands/ICommandManager/).

## Импорт пакета

Возможно, вам потребуется импортировать пакет, если вы столкнетесь с какими-либо проблемами, так что лучше быть безопасным чем извините и добавьте импорт.  
`import mods.contenttweaker.Commands;`

## Вызов команды

Это единственное, что вы можете сделать с пакетом команд.

```zenscript
вызов (String команды, IPlayer игрока, IWorld world)
вызова (String команда, IPlayer игрока, мира IWorld, logToChat, логическое переопределение разрешений)
```

Параметры:

- Команда строки → Команда, которая будет выполнена
- [IPlayer](/Vanilla/Players/IPlayer/) игрок → Игрок, выполняющий команду
- [IWorld](/Mods/ContentTweaker/Vanilla/Advanced_Functionality/Commands/) мир → мир, в котором выполняется команда
- boolean logToChat → Должен ли вывод команды появиться в MC чате?
- boolean переопределение прав доступа должно выполняться вне зависимости от требуемого уровня разрешений?

Оба логических значения необходимо либо добавлять, либо пропускать. Если вы вызовете команду без них, они будут правдой.