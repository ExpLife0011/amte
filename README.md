# Intro (russian)

Обфускация бинарных модулей является интересным направлением в области усложнения исполняемых файлов, а также сокрытия целевого функционала от аналитиков и конкурентов. Как-то это банально, но для большинства это приемлемая и понятная формулировка.

На этот проект было потрачено около 2-х месяцев в 2013 году. Однако не столько интересен сам проект, потому что он является сильно устаревшим и требует значительного творческого вложения, чтобы стать по-настоящему достойным решением, а сколько исходная формулировка задачи и формирование оккультного базиса, использующихся здесь.

Будучи системным инженером и методологом (или просто маргиналом) я всегда люблю при формулировке задач обращаться сразу к нескольким сферам, особенно к оккультной стороне реальности, в которой скрыто очень много секретов для тех, кто понимает о чём я говорю.

Во-первых, такой стиль позволяет создавать системы, концептуально схожие с чем-то, что уже было порожено природой и отлаживалось веками людьми, джинами и духами. Во-вторых, обобщение к которому приходишь так или иначе, позволяет судить о том, что разрабатываемая система имеет под собой серьёзные основания и базируется на проверенных общесистемных принципах.

Более того, математикам известно, что если не возможно решить проблему в одной алгебраической системе в силу недостаточности данных, то самым простым подходом будет способ решения задачи в другой алгебраической системе изоморфной относительно категорий и исходных неделимых элементов, а потом перенести результаты в исходную алгебраическую систему.

При разработке этого инструмента, я решил взять некоторые свои наблюдения и опыт из оккультной практики с закреплением эфемерных существ в конструкцию тонких тел человека. А точнее приблизительно разобраться и с самой оккультной стороной этих вещей, дабы пролить немного света на тему с дьяволом и экзорцизмом.

Известно, что не всякий дизайн человека позволяет такому внедрению осуществляться. Причин несколько:

1. Различные эфемерные существа имеют различную структуру.
2. Человеческие существа, а точнее конгломерат их тонких тел также не имеет однозначной структуры.
3. Сама процедура подселения сущности (джина, гоблина) является весьма сложной, но по моим допущениям также проистекает из общесистемных принципов.

Всем нетрадиционным разаботчикам малвари известен принцип, что в своей сфере не следует пользоваться стандартизированным подходом к разработке, потому что, такой подход не является правильным по многим причинам. Об этом можно говорить много и я не хочу здесь ставить акцент на этом вопросе. Однако это также позволяет провести параллель между одухотворённой реальностью и исполняемыми файлами с малварей.

Итак, мы имеем:

- Одухотворённое существо (например, человек) можно соотнести с легитимным исполняемым файлом. У обоих однозначная и стандартизированная базовая структура, приспособленная к модификации.
- Эфемерная щусность (паразит) мы соотнесём с malware-системой. Они также принципиально схожи как идейно, так и структурно и также способны мутировать.

Формулировка задачи теперь сводится к тому, каким образом возможно внедрить malware-паразита в структуру легитимной сущности, так, чтобы:

1. Легитимная сущность осталась структруно нетронутой (в зачительной мере).
2. При активации сущности (запуске исполняемого файла) контролем обладал malware-паразит.
3. Было трудно обнаружить само подселение по исходным признакам. Например, если паразит подселяется к человеку, человек также способен выполнять свои базовые задачи, но со значительным искажением и не меняясь во внешем виде. Как правило эфемерная сущность завладевает не всеми аспектами, а например только сознательным аппаратом, чтобы манипулировать действиями человека.
4. Было достаточно сложно произвести анализ того, как именно паразит закрепился.

Теперь мы имеем теоретический базис (но далеко не полный), остаётся только реализовать это всё в знакомой алгебраической системе - в сфере кибернетики, и перенести выводы на оккульную сферу.

Код любого приложения на уровне ассемблера можно разбить на базовые неделимые блоки. Критерий формирования базовымх блоков (без углубления) прост - это блоки между условными и безусловными переходами.

Поэтому в простом изложении, алгоритм будет следующим:

1. Необходимо разбить на базовые блоки бинарный вариант легитимного PE-файла в который будет происходить внедрение.
2. Аналогично, разбить на базовые блоки нашего паразита.
3. Произвести перемешивание блоков таким образом, чтобы функционально ход исполнения обоих был идентичен тому, который соответствует оригинальной структуре.
4. Для каждого базового блока паразита найти один или более базовых блоков легитимного модуля.
5. И если для всех базовых блоков паразита найдены такие подходящие базовые блоки заражаемого модуля (их может не быть, быть только один или несколько), то заместить базовые блоки в орининальном модуле на базовые блоки паразита, скорерктировав переходы между блоками.
6. Обеспечить несколько дополнительных мутаций с целью усложенния будущего анализа (в частности, чтобы коэффициент энтропии секции кода был очень близок к исходного коэффициенту).
7. Пересобрать исходный PE-модуль. При этом не забываем, что модифицироваться должно как можно меньше секций легитимного модуля.
8. Profit. Наш паразит закреплён.

Какие выводы можно сделать:

1. Не для каждого паразита можно подобрать исходный легитимный модуль. Также как и не каждому человеку можно подселить эфемерную сущность в силу разных причин.
2. Сущесвует способ модификации легитимного модуля, которая позволит повысить его иммунитет к подселению паразитов.
3. Исходная PE-структура malware-паразита должна быть максимально минималистичной (например иметь только секцию кода) и для увеличения потенциала внедрения должна обладать максимально гибкой структурой, которую можно разбить на приемлемые базовые блоки для успешного внедрения. Аналогично, эфемерные сущности должны обладать высокими мутационными характеристиками. 

Такова история этого простого обфускатора ;)

Для заинтересованных могу сказать, что это всего лишь базис, на котором можно выстроить гораздо более сильную математически обоснованную теоретическую конструкцию и подвести её к общесистемным законам.

## Послесловие

Этим кратким изложением я хотел показать тем парням и девушкам, которые неравнодушны к темам вирусологии и malware-писательсву, что зачастую, формулировка задачи как можно более нетрадиционным способом может дать положительные и изящные результаты, которые можно применять на практике.

Надеюсь это краткое изложение будет полезно как malware-творцам, так и их достойно оппощиции. Всем вам, мой низкий поклон.

Будьте творцами с большой буквы, выбирайте для себя только нравственный путь и не обижайте слабых!

# Intro (english)

*Note: Who is ready to translate the description from russian, you can do it through the PR or send it to me by email and I'll post it here.*

`Comming soon...`
