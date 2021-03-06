# MCPotionEffectInstance

Этот класс был добавлен модом с mod-id `crafttweaker`. Так что если вы хотите использовать эту функцию, вам нужно установить этот мод.

## Импорт класса
Вам может потребоваться импортировать пакет, если вы столкнетесь с какими-либо проблемами (например, с заливкой массива), так что лучше быть в безопасности, чем извиняться и добавлять импорт.
```zenscript
crafttweaker.api.potion.MCPotionEffectInstance
```

## Methods
### addCurativeItem

```zenscript
myMCPotionEffectInstance.addCurativeItem(stack as crafttweaker.api.item.IItemStack);
```

| Параметр | Тип                                                               | Description          |
| -------- | ----------------------------------------------------------------- | -------------------- |
| stack    | [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack) | Описание отсутствует |


### combine

Return type: boolean

```zenscript
myMCPotionEffectInstance.combine(effect as crafttweaker.api.potion.MCPotionEffectInstance);
```

| Параметр | Тип                                                                                           | Description          |
| -------- | --------------------------------------------------------------------------------------------- | -------------------- |
| effect   | [crafttweaker.api.potion.MCPotionEffectInstance](/vanilla/api/potions/MCPotionEffectInstance) | Описание отсутствует |


### getCurativeItems

Тип возврата: Список&lt;[crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack)&gt;

```zenscript
myMCPotionEffectInstance.getCurativeItems();
```

### isCurativeItem

Return type: boolean

```zenscript
myMCPotionEffectInstance.isCurativeItem(stack as crafttweaker.api.item.IItemStack);
```

| Параметр | Тип                                                               | Description          |
| -------- | ----------------------------------------------------------------- | -------------------- |
| stack    | [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack) | Описание отсутствует |


### setCurativeItems

```zenscript
myMCPotionEffectInstance.setCurativeItems(items as crafttweaker.api.item.IItemStack[]);
```

| Параметр | Тип                                                                 | Description          |
| -------- | ------------------------------------------------------------------- | -------------------- |
| items    | [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack)[] | Описание отсутствует |



## Свойства

| Название      | Тип                                                                           | Имеет Getter | Имеет Setter |
| ------------- | ----------------------------------------------------------------------------- | ------------ | ------------ |
| ambient       | boolean                                                                       | true         | false        |
| amplifier     | int                                                                           | true         | false        |
| duration      | int                                                                           | true         | false        |
| effectName    | String                                                                        | true         | false        |
| potion        | [crafttweaker.api.potion.MCPotionEffect](/vanilla/api/potions/MCPotionEffect) | true         | false        |
| showIcon      | boolean                                                                       | true         | false        |
| showParticles | boolean                                                                       | true         | false        |

