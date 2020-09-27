# Ассоциативные массивы

Объединенный массив (иногда называемый картой или словарь) является нормальным [массивом](/AdvancedFunctions/Arrays_and_Loops/) таким образом, чтобы он мог хранить несколько записей. Однако, в отличие от [массивов](/AdvancedFunctions/Arrays_and_Loops/) , вы можете выбрать, какой тип вы хотите индексировать или (как мы называем его на картах), чтобы быть!

## Объявление ассоциативного массива

Ассоциативные массивы объявляются с помощью фигурных скобок`{}` и двоеточий `:`.

```zenscript
val myAssocArray = {
    dirt : <minecraft:dirt>,
    gold : <minecraft:gold_ingot>
} as IItemStack[string];
```

Давайте разберемся с этим, да?

- `val myAssocArray =` — стандартное объявление переменной,
- `{` — ассоциативный массив, сэр!
- `dirt : <minecraft:dirt>` — мы присваиваем значение `<minecraft:dirt>` к ключу `dirt`,
- `,` подождите, пришло больше
- `Золото : <minecraft:gold_ingot>` мы карту `<minecraft:gold_ingot>` под строкой `золото`
- `}` мы достигли конца массива, господин!
- `в качестве IItemStack[string];` это ассоциативный массив, который использует строки в качестве индикаторов и IItemStacks в качестве значений.

Окей, что мне нужно подумать насчет использования всего этого?

- Вы можете использовать около каждого типа, доступного Zenscript как ключ или значение.
- Вы не можете использовать переменные для определения ключа в начальном объявлении (тот, который использует `{}`), как строку!

## Обращение к элементам ассоциативного массива

Вы ссылаетесь на предметы внутри ассоциативного массива так же как вы относитесь к предметам внутри обычного [массива](/AdvancedFunctions/Arrays_and_Loops/):  
`Массив[index]`  
Только разница в это время, вам не обязательно использовать целое число в качестве индекса, но какой бы тип вы назвали ваш массив!

```zenscript
<br />val dirt = <minecraft:dirt>;
val assocArray = {
    <minecraft:dirt> : "Это я"
} как строка[IItemStack];

//массив[index]
print(assocArray[<minecraft:dirt>]);

//Вы также можете использовать переменную переменной
print(assocArray[dirt]);
```

Существует один особый случай, то есть когда вы используете строки как indecs:  
В этом случае вы можете также использовать memberGetter как таковый:

```zenscript
val assocWithStrings = {
    //вы можете использовать "" если хотите
    "один" : "1",

    //но вам не нужно
    два : "2"
} как строка[string];

//Вы можете использовать memberGetter
print(assocWithStrings. ne);

//Или стандартный индекс Getter
print(assocWithStrings["two"]);
```

## Манипулирование элементами внутри ассоциативного массива

Как и в массивах, вы можете манипулировать предметами внутри ассоциативного массива, используя `массив[index] = newValue`.  
Существует одно существенное различие:  
Хотя массивы имеют фиксированный размер, карты не поддерживаются. Это означает, что вы всегда можете добавить запись, установив индекс, который ранее не был установлен!

```zenscript
val changingArray = {
    <minecraft:dirt> : "это я",
    <minecraft:gold_ingot> : "и я ненавижу его"
} как строка[IItemStack];

val gg = <minecraft:gold>;

//Переопределяет значение gold_ingot
changingArray[gg] = "и мне нравится";

//добавляет новую запись
changingArray[<minecraft:grass>] = "Power!";
```

## Получение ключа и входов в ассоциированный массив

KeySet - это массив, содержащий все ключи карты.  
valueSet - массив, содержащий все значения карты.  
Набор записей представляет собой массив, содержащий все записи карты (см. ниже).

```zenscript
myAssocArray.keySet //keySet
myAssocArray.keys //keySet
myAssocArray.values //valueSet
myAssocArray.valueSet //valueSet
myAssocArray.entrySet //entrySet
```

## Перебор ассоциативного массива

Есть два итератора, которые позволяют вам повторить над ассоциативным массивом:

- Ключ-итератор: Итерация поверх клавиш, использует одну переменную
- Ключевое значение-Iterator: Итерация над ключами и значениями, использует две переменные

Давайте добавим ассоциативный массив, в котором хранится рецепты создания для итерации:

- Ключи должны быть выходом ремесла как [IItemStack](/Vanilla/Items/IItemStack/)
- Значения должны быть компонентами создания как [IIngredient](/Vanilla/Variable_Types/IIngredient/)
- Мы будем использовать ключ Итератор, который построен так: `для ключа assocArray {doSth;}`
- Мы также будем использовать ключ-value-Iterator, который построен как это `для ключа, значение в assocArray {doSth;}`

```zenscript
импорт crafttweaker.item.IItemStack;
import crafttweaker.item. Ингредиент;

val dirt = <minecraft:dirt>;
val recipeMapShaped = {
    <minecraft:grass> : [[dirt, dirt, dirt],[dirt, dirt],[dirt, dirt, dirt]],
    <minecraft:gold_ingot> : [[грязь, грязь, грязь],[грязь, <minecraft:gold_ingot>, грязь],[грязь, грязь, грязь]]
} как IIngredient[][][IItemStack];

recipeMapShaped[dirt] = [[dirt, dirt, dirt],[dirt, null, dirt],[dirt, dirt]];

//ключом будет трава, goldIngot, грязь
для ключа в рецептах recipeMapShaped {
    . ddShaped(ключ, рецепт формы[key]);
}


//ключи будут травами, goldIngot, грязью, значениями будут рецепты для них
для ключа, значение в рецепте recipeMapShaped {
    рецептов. ddShaped(ключ, значение);
}
```

# Запись ZenType

Запись карты состоит из ключа и значения.  
В настоящее время единственным способом получения такого объекта является метод entrySet карты.

Вы можете использовать getters чтобы получить `ключ` и `значение`

```zenscript
//Замените карту ссылкой на существующий массив карты/ассоциативный
myEntry = map.entrySet[0];


myEntry.key; //Возвращает ключ записи.
myEntry.value; //Возвращает значение записи.
```