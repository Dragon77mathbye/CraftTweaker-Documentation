### Класс

```zenscript
Импортировать mods.roots.Transmutation;
```

#### Методы

```zenscript
void removeRecipe(
  string name // название рецепта, который будет удален
);
```

* * *

```zenscript
void addBlockToBlockRecipe(
  строковое имя, // имя добавляемого рецепта (должно быть уникальным)
  IBlockState state1, // исходное состояние блока, определенного как блокирующее состояние
  IBlockState state2 // состояние, в котором исходное состояние должно быть преобразовано в
);
```

* * *

```zenscript
void addBlockToItemRecipe(
  имя строки, // имя добавляемого рецепта (должен быть уникальным)
  состояние IBlockState // исходное состояние, которое ищется при преобразовании (в виде состояния блока)
  IItemStack стека // стек элементов, заменяющий состояние блока
);
```

* * *

### Примеры

```zenscript
импортируем mods.roots.Transmutation;

// Удаляем рецепт по умолчанию тыквен-овер-арк-дыня
Transmutation.removeRecipe("pumpkin_melon");

// Добавляет рецепт, преобразующий конечный камень в блоки костной ткани
Трансмутации. ddBlockToBlockRecipe("end_stone_to_bone", <blockstate:minecraft:end_stone>, <blockstate:minecraft:bone_block:axis=y>);

// Добавляет рецепт, который преобразует высокие травы по умолчанию в снежки
Трансмутацию. ddBlockToItemRecipe("tallgrass_to_snowball", <blockstate:minecraft:tallgrass:type=tall_grass>, <minecraft:snowball>*3);
```

### Примечания

**Примечание: функции сложных состояний в настоящее время не доступны через CraftTweaker (например, проверка окружения).**

Можно найти информацию о блоке и его вариантах и состояниях с помощью функции отладки F3 и таргетинга по нему. В правой части экрана будет отображено имя реестра блока, а затем все указанные ниже состояния.

Например, `bone_block` имеет следующее:

    оси: у

Это может быть преобразовано в блочное состояние, заменив `:` на `=` как: `axis=y`, означает, что конечным блокстати (для лобового блока вверх) будет `<blockstate:minecraft:bone_block:axis=y>`.