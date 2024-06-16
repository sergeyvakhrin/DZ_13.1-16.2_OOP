# DZ_OOP_13.1-16.2

# dz_13.1

Создайте классы Product и Category.

Для класса Product:

название (name),
описание (description),
цена (price),
количество в наличии (quantity).
Для класса Category определите следующие свойства:

название (name),
описание (description),
список товаров категории (products).
Для этих двух классов, добавьте инициализацию так, чтобы каждый параметр был передан при создании объекта и сохранен.

Также для класса Category добавьте два атрибута класса. Доступ к этим атрибутам должен быть у каждого объекта класса и в них должна храниться общая информация для всех объектов. Эти атрибуты хранят в себе количество категорий и количество товаров. Атрибуты класса должны заполняться автоматически при инициализации нового объекта.

# dz_13.2

Для класса Category сделайте список товаров приватным атрибутом, чтобы к нему нельзя было получить доступ извне.
Для добавления товаров в категорию реализуйте специальный метод, в который нужно передавать объект класса Product и уже его записывать в приватный атрибут списка товаров.
Так как вы сделали атрибут со списком товаров приватным, то атрибут «список товаров категории» у вас освободился, но вы лишили программу возможности выводить список товаров. Чтобы вернуть возможность просмотра товаров, нужно реализовать геттер, который будет выводить список товаров в виде строк в формате:

Название продукта, 80 руб. Остаток: 15 шт.

Для класса Product необходимо создать класс-метод new_product, который будет принимать на вход параметры товара и возвращать созданный объект класса Product.

Для класса Product сделайте атрибут цены приватным и опишите геттеры и сеттеры. В сеттере реализуйте проверку: в случае если цена равна или ниже нуля, выводите сообщение в консоль “Цена не должна быть нулевая или отрицательная”, при этом новую цену устанавливать не нужно.

# dz_14.1

Для класс Product добавить строковое отображение в следующем виде:

Название продукта, 80 руб. Остаток: 15 шт.

В предыдущей домашке вы делали геттер для класса Category для вывода списка товаров, теперь каждый продукт имеет реализованное строковое отображение. Вы можете вернуться к этому геттеру и оптимизировать его работу, просто преобразовав объект продукта в строку.

Для класса Category добавить строковое отображение в следующем виде:

Название категории, количество продуктов: 200 шт.

Для удобства работы с продуктами реализовать возможность их складывать. Логика сложения должна работать так, чтобы в итоге у вас получалась полная стоимость всех товаров на складе. Например, для товара a с ценой 100 рублей и количеством на складе 10 и товара b с ценой 200 рублей и количеством на складе 2 результатом выполнения операции a + b должно стать значение, полученное из 100 * 10 + 200 * 2 = 1400.

# dz_15.1

Для магазина необходимо выделить две категории товаров и создать под них классы:

Смартфон (Smartphone)

Помимо имеющихся свойств, необходимо добавить следующие:

производительность (efficiency),
модель (model),
объем встроенной памяти (memory),
цвет (color).
Трава газонная (LawnGrass)

Помимо имеющихся свойств, необходимо добавить следующие:

страна-производитель (country),
срок прорастания (germination_period),
цвет (color).
Эти оба класса должны быть классами-наследниками от исходного класса Product.

Доработайте функционал сложения таким образом, чтобы можно было складывать товары только из одинаковых классов продуктов.

То есть новый функционал не должен давать возможность сложить смартфон и траву газонную, вместо этого, должна быть выдана ошибка TypeError.

Для решения этого задания воспользуйтесь функцией type().

Ранее мы реализовали отдельный метод, с помощью которого можно добавлять объекты продуктов в категории. Теперь защитим метод так, чтобы, кроме смартфонов, травы газонной или других продуктов, в список нельзя было добавлять ничего другого.

Доработайте метод, который добавляет продукт в категорию таким образом, чтобы не было возможности добавить вместо продукта или его наследников любой другой объект.

Для решения этой задачи воспользуйтесь проверкой на issubclass() или isinstance().

# dz_15.2

Создайте базовый абстрактный класс с именем BaseProduct, который станет родительским для класса продуктов. Классы «Смартфон» и «Трава газонная» остаются наследниками класса Product и тем самым наследуют все свойства абстрактного класса.

Важно выделить общий функционал, который должен быть у каждого продукта, и описать его в абстрактном классе.

Реализуйте класс-миксин, который будет при создании объекта, то есть при работе метода __init__, печатать в консоль информацию о том, от какого класса и с какими параметрами был создан объект.

Например:

Product('Продукт1', 'Описание продукта', 1200, 10)

Добавьте миксин в цепочку наследования класса Product.
