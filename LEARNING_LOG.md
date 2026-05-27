### YYYY-MM-DD — Day 1 — Basic Syntax: класс-обёртка + имя файла = имя класса

**Pomodoros:** ?/3 (50/10) — заполни сам
**Roadmap progress:** Phase 1 — Basic Syntax — структура файла, класс, точка входа `main`

**Что освоил сегодня (своими словами, без copy-paste):**

- В Java любой код обязан жить внутри класса. Нет верхнего уровня как в JS/Python.
- Внутри класса лежат **методы** (methods) — это то, что в JS зовут "function", когда она живёт внутри класса.
- Для `public class X` файл ОБЯЗАН называться `X.java`. Это правило проверяет компилятор `javac`.
- Причина обёртки в класс: JVM умеет загружать и запускать только классы как единицы. Свободно стоящий код JVM не умеет — у неё нет такого API.
- `javac` и `java` — две разные программы. `javac HelloWorld.java` создаёт `HelloWorld.class` (bytecode). `java HelloWorld` уже просит JVM загрузить и запустить класс.

**Своими словами объясняю Feynman:**

> JVM ищет карандаши по цвету (по имени класса). Если на карандаше написано "розовый", а сам он красный — JVM замечает и указывает на ошибку. Если имя на карандаше совпадает с тем, что ищет — принимает. Так объясняется правило `имя_файла = имя public_class`.
> Дополнительно: код в Java обязан жить внутри класса, потому что у JVM нет команды "выполни вот этот свободный кусок" — только "загрузи класс по имени и запусти его main".

**Код, который я написал сегодня:**

- `hello-world/HelloWorld.java` — выводит "Привет, Java!"

**Ошибки, которые я сделал:**

1. Сначала написал `public class Goodbye` внутри `HelloWorld.java` — компилятор: _"class Goodbye is public, should be declared in a file named Goodbye.java"_. Понял правило `file_name = public_class_name`.
2. В Feynman перепутал ДВА вопроса: "почему класс-обёртка вообще нужна" vs "почему имя файла должно совпадать с именем класса". Ответил на второй вместо первого.
3. Назвал JVM "компилятор JVС" — спутал `javac` (компилятор) и JVM (виртуальная машина). К Phase 3 разберу подробно.

**Что осталось непонятным:**

- Что значат `public`, `static`, `void`
- Что такое `String[] args` (массив аргументов — но зачем?)
- Почему `System.out.println` пишется через точки, что за `.out`
- Зачем точки с запятой и фигурные скобки

**Retrieval-test results:**

- Первый день, ретривить нечего.

**Следующая сессия начинается с:**

- Retrieval: почему код в Java живёт в классе? что делает `javac` vs `java`? что будет если в `Foo.java` написать `public class Bar`?
- Новая тема: оставшиеся куски Basic Syntax — точки с запятой, фигурные скобки, комментарии, разбор сигнатуры `main`.

**Memory update для Claude:**

> Day 1 done. Closed: class wrapper required (JVM loads classes-as-units), file_name == public_class_name rule, javac vs java distinction. Open: meaning of public/static/void/String[] args, semicolons/braces. Compiler vs JVM conflated once — flagged. Repo: github.com/nlysiuk/java-learning.

**Anti-pattern check:**

- [x] Писал код руками без copy-paste — да (написал "Привет, Java!" вместо "Hello, Java!")
- [x] Feynman делал — да, 2 из 3 пунктов с первого раза, (а) пришлось переотвечать
- [ ] Retrieval — N/A первый день
- [ ] Закоммитил код в GitHub — ЕЩЁ НЕТ
