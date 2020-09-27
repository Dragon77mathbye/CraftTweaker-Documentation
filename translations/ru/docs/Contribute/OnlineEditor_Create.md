# Создать файлы с помощью онлайн-редактора GitHub

## Требования

Вам нужно будет создать учетную запись GitHub и [форкнул вики к вашему аккаунту](/Contribute/SetupGithub).

## Введение

Онлайн-редактор GitHub позволяет изменять и создавать файлы, ничего не используя браузер.  
Возможно, это не так универсально, как [с использованием локальной копии](/Contribute/LocalClone/CreateCommit/) , но вам не нужно беспокоиться о [настройке git](/Contribute/LocalClone/InstallingGit/) и всех.

Это руководство покажет вам, как создать новый файл вики с помощью онлайн редактора github.  
Ваша основная причина добавления новых страниц скорее всего заполнит недостающую информацию, но, возможно, вы также хотите добавить пример записи вики для определенного обработчика модов, любая причина, не стесняйтесь зафиксировать изменения и в конечном итоге [файл Pull Request](/Contribute/PullRequest).

Однако помните, что вам нужно создать английскую версию, Затем переводы обрабатываются через [CrowdIn](https://crowdin.com/project/crafttweaker-documentation/) (но только после слияния PR).

## Где создать файл

Теоретически это не имеет значения, где вы поставили свой файл, но попробуйте подобрать текущую схему:

- Все файлы должны находиться в папке `с` документацией.
- Структура файла должна совпадать с цепочками панели навигации. Пример: При использовании навигационной панели в вики, `ICraftingRecipe` можно найти в `Vanilla/Recipes/Crafting Table Recipes/ICraftingRecipe` Файл рецепта ICraftingRecipe можно найти на `docs/Vanilla/Recipes/Crafting/ICraftingRecipe.md`. Как вы можете видеть, пути не точно совпадают, но они достаточны, чтобы найти файл.
- Вся информация для одного мода должна оставаться в одной группе/папке.

## Создать файл

После того, как вы успешно разместили путь к файлу в будущем, перейдите в папку, которая будет содержать файл в GitHub, если он существует.  
Не беспокойтесь, если он не существует, вы можете создать файл.

Скажите что вы хотите создать файл с именем `Secret_Information. d` в `документа/AdvancedFunctions`:  
Найти путь в GitHub и нажмите `Создать новый файл` ![Создать кнопку Файла](/Contribute/assets/OnlineEditor_CreateFileButton.png)

Теперь вы можете просмотреть новую страницу редактора файлов.  
Вначале вы увидите путь к файлу, который будет создан. Если мы хотим, чтобы файл был создан в точно каталоге, который отображается в пути, нам нужно предоставить только название файла и расширение. Помните, что все файлы wiki должны иметь расширение `.md` , так как эта вики использует markdown.

Если вы хотите, чтобы файл был создан в (возможно не существующих) подпапке, или даже несколько папок вниз по пути, вы можете использовать `/` для разделения имен папок (как вы уже можете видеть в данном пути).

Редактор позволяет создать файл так, как вам нравится, а также непосредственно просмотреть скомпилированное форматирование.

Если синтаксис файлов является для вас новым, в вики используется MarkDown. Там должно быть много уроков, чтобы найти с помощью Google (или вы могли бы добавить один прямо здесь, на этой вики, если хотите).

## Добавить файл к индексу

После того, как вы создали файл и закомментировали создание (см. ниже), вам также нужно будет добавить файл в индекс, , чтобы позже его можно было отобразить на панели навигации.

Этот индекс является файлом `mkdocs.yml`.

Этот файл содержит все, что необходимо для создания wiki, и вам нужно убедиться, что это не ломается (хотя мы расскажем вам, что ваш PR ломает сборку, которая должна прийти к этому)!

Все, что вам нужно сделать, это добавить свой файл и категории в `список` страниц.  
Формат довольно прост вперед:

- Записи начинаются с `-`
- Затем приходит (показано, английский) имя для группы или записи, затем `:`
- Если вы создаете группировку (например, `Vanilla` или `моды`) переходите к следующей строке, пробелы в строке.
- Если вы создаете фактическую ссылку на файл страницы, добавьте его на ту же строку, после `:` и пробел. Обязательно оберните его в одинарные кавычки `'` , чтобы убедиться, что сборка работает, как ожидалось. Путь относительно папки `docs` , поэтому `docs/Vanilla/Commands.md` становится `Vanilla/Commands.md`.

Для примеров смотрите [текущий mkdocs.yml файл на github](https://github.com/CraftTweaker/CraftTweaker-Documentation/blob/master/mkdocs.yml). Кроме того, отредактируйте этот файл и добавьте свой собственный пример здесь.

## Сохранить/Зафиксировать изменения

*Замечание: Это описание происходит из руководства по редактированию, но те же принципы применяются, если это необходимо, подменяют вашу собственную версию*

После того, как вы создали содержимое файла, вам нужно сообщить GitHub о том, что вы хотите сохранить изменения.

Это поле коммитов ниже вашего редактора:  
Вы не можете просто сохранить файл, вы должны предоставить краткую информацию о том, что вы делали (коммиты) и краткое описание, в котором вы можете добавить дополнительную информацию, например, почему вы делали изменения или что именно было изменено.

По умолчанию оно выглядит примерно так:  
![Строка фиксации по умолчанию](/Contribute/assets/OnlineEditor_CommitBox_Default.png)

В этом примере название коммита (или отредактируйте сводку) — `обновление Arrays_and_Loops.md`. GitHub не может знать, что должны были сделать ваши фактические изменения, поэтому он пытается что-то столь же универсальное.

Вы можете добавить дополнительное название или описание, но это не обязательно, хотя оно делает просмотр вашего Pull запроса позже на проще.

Если у вас есть несколько адресов электронной почты, зарегистрированных для вашей учетной записи GitHub, вы можете выбрать, какой из них вы создадите коммит. Однако это не окажет никакого реального влияния на внесение своего вклада.  
Вы также можете решить, хотите ли вы совершить фиксацию напрямую в свою ветку или создать новую ветку для фиксации. В большинстве случаев принятие обязательств в вашу ветку работает хорошо.

Заполненный пример может выглядеть так: ![Блок коммитов заполнён](/Contribute/assets/OnlineEditor_CommitBox_Filled.png)

## Что делать дальше

После того, как вы зафиксировали изменения, вы можете продолжить и [изменить](/Contribute/OnlineEditor_Edit) или создать больше файлов с помощью онлайн-редактора.  
После того, как вы выполните все ваши изменения, вы можете [создать Pull Request](/Contribute/PullRequest).