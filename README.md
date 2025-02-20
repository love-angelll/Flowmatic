<!-- фото проекта -->
![bg](https://github.com/love-angelll/Flowmatic/blob/main/img/bg.png )
# Flowmatic — электронный дозатор жидкости 
###### от «flow» (поток) и «automatic» (автоматический).  

Flowmatic — это автоматический дозатор жидкости, основанный на известном проекте [Алекса Гайвера](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://alexgyver.ru/about_gyver/&ved=2ahUKEwi2q-HMqdOLAxXq9QIHHc0FFR0QFnoECCYQAQ&usg=AOvVaw1rDqv2uakHtufNj98641UN)' — наливаторе. Этот репозиторий был создан в рамках моей дипломной работы по специальности «[Техническое обслуживание и ремонт радиоэлектронной аппаратуры](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=http://ttiip.ru/technik_2110202.html&ved=2ahUKEwibq_acqdOLAxUN-AIHHZ_fA44QFnoECB0QAQ&usg=AOvVaw1QHKlo13XkNP1YWU1fiTzu )'» в [Тираспольском Техникуме Информатики и Права](https://ttiip.ru/index.php)'.

Проект был выбран для дипломной работы, так как он идеально сочетает теоретические знания и практические навыки, полученные в процессе обучения. В данном репозитории я делюсь всеми материалами, использованными для разработки устройства, включая компоненты, 3D модель корпуса, схемы подключения и другие важные файлы.

### 📃 Описание проекта

Flowmatic представляет собой автоматический дозатор жидкости, который управляет процессом наливания жидкости в ёмкости. Устройство контролирует объем налитой жидкости и автоматически останавливает процесс, когда уровень достигает заданного значения. Это позволяет избежать переполнения ёмкости и оптимизировать расход жидкости.

Целью проекта было создание устройства, которое бы автоматизировало процесс наливания и обеспечивало точность дозирования, что крайне важно в ряде промышленных и бытовых применений. В основе проекта лежат микроконтроллеры Arduino и датчики уровня жидкости, что позволяет точно измерять уровень жидкости в реальном времени и управлять насосом.

#### Система рассчитана на 1-6 рюмок.

### 🌈 Подсветка рюмок

- **Красный** – пустая
- **Жёлтый** – в процессе заполнения
- **Зелёный** – готово к употреблению

### ⚡ Система энергосбережения

- Система “пинания” powerbank’a, не дающая ему уйти в сон.
- Продуманная система энергосбережения:
  - Дисплей снижает яркость при простое.
  - Серво отключается от питания.

### 🔧 Режимы работы

#### 1. **Калибровка (Режим сервиса)**

- Подать питание с зажатой большой кнопкой.
- Дождаться надписи **SERVICE**.
- Энкодер управляет положением крана, на дисплей выводится угол.
- Кнопка энкодера запускает помпу и таймер.
- Удержание большой кнопки – выход из сервиса в обычный режим работы.

#### 2. **Ручной режим**

- Буква **Р** в левом краю дисплея.
- Выставляем стаканчики и кликаем по кнопке.
- Во время цикла заполнения можно доставить стакан, он будет заполнен.

#### 3. **Автоматический режим**

- Смена режимов – удержание большой кнопки.
- Буква **А** в левом краю дисплея.
- Каждый поставленный стаканчик будет заполнен!

### ⚙️ Общие особенности

- Если поднять стакан до заполнения, помпа отключится, и система перейдёт к следующему стакану.
- Если наблюдаются глюки (неправильное положение крана при заливке, промахи) – проблема в питании! Попробуйте добавить конденсаторы как на схеме, попробуйте другой powerbank, а ещё лучше проверить работу системы на нормальном зарядном блоке питания от смартфона. Система многократно протестирована, работа отлажена, неадекватное поведение замечено при плохом питании.

### 🔋 Поддержание питания

Практически все powerbank’и отключают линию питания при отсутствии нагрузки. Для этого в системе предусмотрено периодическое подёргивание сервопривода с целью создания скачков нагрузки, которые вынуждают powerbank не уходить в сон и не отключать наливатор от питания.

- В этом режиме система будет каждые 15 секунд дёргать приводом и мигать дисплеем.
- Если вам это не нужно – отключите настройку `KEEP_POWER`, присвоив ей 0 вместо 1.

### 📦 Включенные материалы

- Компоненты
- 3D модель корпуса
- Схемы подключения
- И другие файлы, необходимые для реализации проекта

### 📅 Информация о проекте

Проект был создан в рамках дипломной работы и направлен на практическое применение знаний и навыков в области электроники и программирования.

### 🔧 Основные возможности

- Автоматическое дозирование жидкости с высокой точностью.
- Режимы: ручной и автоматический.
- Регулируемый объём жидкости.
- Визуальный интерфейс на дисплее (отображение режима работы, объёма).

### 🧰 Элементная база компонентов

В этом разделе перечислены основные компоненты, используемые в проекте **Flowmatic** — автоматическом дозаторе жидкости.

| **Компонент**                 | **Описание**                                                                 | **Количество**  | **Примечания**                                                 |
|-------------------------------|-----------------------------------------------------------------------------|-----------------|--------------------------------------------------------------|
| **Arduino Nano ATMega328**     | Микроконтроллер для управления системой.                                      | 1               | Главное устройство управления.                                |
| **Адресная лента**             | Лента с адресными светодиодами, различных типов (IP30, IP65, IP67).           | В зависимости от проекта | Цвет подложки: Black PCB / White PCB.                         |
| **Энкодер**                    | Устройство для управления углом вращения.                                    | 1               | Для точного управления движением.                             |
| **Кнопка**                     | Кнопка для управления устройством.                                           | 1               | Для включения/выключения или других действий.                  |
| **Дисплей TM1637**             | Дисплей для отображения информации.                                          | 1               | Используется для вывода информации о состоянии устройства.     |
| **Концевик**                   | Механический датчик положения.                                               | В зависимости от проекта               | Для точного определения положения объекта.                     |
| **Драйвер MX1508**             | Моторный драйвер для управления моторами.                                    | 1               | Для управления мощными моторами или сервоприводами.            |
| **Сервопривод**                | Механизм для точного управления положением.                                 | 1               | Для точного регулирования механизма или подачи жидкости.       |
| **Модуль USB**                 | Модуль для подключения устройства к компьютеру или другому USB-устройству.   | 1               | Для подключения и обмена данными.                              |
| **Помпа**                      | Насос для подачи жидкости в ёмкость.                                         | 1               | Для автоматического наливания жидкости в ёмкость.              |


### 🗺️ Схема проекта

<div align="center">
  <img src="https://github.com/love-angelll/Flowmatic/blob/main/Project%20Files/sheme.jpg" alt="sheme">
  <h6>Схема, по которой было все сделано.</h6>
</div> 

<!--
### 📷 Фото моего готового проекта

![Карусель](https://github.com/love-angelll/Flowmatic/blob/main/Project%20Files/sheme.jpg) 
-->


<!-- Официальные источники и лицензия -->

---

### 🎓 Источники проекта «Наливатор» — Алекса Гайвера

##### Flowmatic основан на проекте Алекса Гайвера, подробности которого можно узнать в его видео и иных его источниках:


<div align="center">
  <a href="https://youtube.com/@alexgyvershow" target="_blank">
    <img src="https://img.shields.io/badge/YouTube-Канал-red?style=for-the-badge&logo=youtube" alt="YouTube Channel">
  </a>
  
  <a href="https://www.youtube.com/watch?v=VNx4pFdzfI4" target="_blank">
    <img src="https://img.shields.io/badge/YouTube-Наливатор-red?style=for-the-badge&logo=youtube" alt="YouTube Nalivator">
  </a>
  
  <a href="https://github.com/AlexGyver/GyverDrink/" target="_blank">
    <img src="https://img.shields.io/badge/GitHub-Проект-black?style=for-the-badge&logo=github" alt="GitHub Repo">
  </a>

  <a href="https://alexgyver.ru/gyverdrink/" target="_blank">
    <img src="https://img.shields.io/badge/Site-Наливатор-blue?style=for-the-badge&logo=google-chrome" alt="Nalivator Site">
  </a>
  
  <a href="https://community.alexgyver.ru/threads/der-nalivator-modificirovannaja-versija-gyverdrink.4021/" target="_blank">
    <img src="https://img.shields.io/badge/Forum-Обсуждение-blue?style=for-the-badge&logo=google-chrome" alt="Forum">
  </a>
</div>

### ⚖️ Лицензия

Данный проект свободно распространяется для любых нужд. При использовании укажите источник.

##### Моя лицензия: [LICENSE](LICENSE)
##### Лицензия Алекса Гайвера: [LICENSE](https://github.com/AlexGyver/GyverDrink/blob/master/LICENSE)

<!-- Конец README.md -->
<p align="center">
  © Иван Фрунза
</p>


















<!--
1. **Микроконтроллер** – Arduino Nano  
2. **Адресная светодиодная лента** – WS2812B  
3. **Энкодер** – KY-040 (для выбора режимов)  
4. **Кнопка** – тактовая кнопка 12×12 мм (для подтверждения выбора)  
5. **Дисплей** – TM1637 или OLED 0.96" (для отображения информации)  
6. **Реле** – 4-канальное реле 5 В (управление насосами)  
7. **Блок питания** – 12 В, 5 А  
8. **DC-DC преобразователь** – 12 В → 5 В (для питания Arduino и других компонентов)  

### 🔩 Механические и гидравлические части  
9. **Перистальтический насос** – 12 В (4 шт.)  
10. **Силиконовые трубки** – внутренний диаметр 4-6 мм  
11. **Клапаны обратные** – предотвращают обратный поток жидкости  
12. **Корпус** – изготовленный из акрила, пластика или дерева  
13. **Держатели и крепления** – для фиксации компонентов  

### ⚙️ Дополнительно  
14. **Проводка и разъёмы** – соединительные провода, клеммы, клеммные колодки  
15. **Программное обеспечение** – код на Arduino (C++)  
16. **Корпус** – для установки всех компонентов
-->


