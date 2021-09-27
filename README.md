# road-to-ios-dev
# Раздел 2: Xcode Storyboards and Interface Builder 
  Иконки и изображения хранятся в папке Assets.xcassets. Иконки и изображения необходимо делать в нескольких форматах. 
  Для подгона под эппловские форматы существует сайт https://appicon.co/.
# Раздел 4: Swift Programming Basics - Collections, Constants and Variables
  Наиболее часто используемые виды content mode:
    aspect fit - свои размеры
    scale to fill - растягивает картинку по размерам экрана
    aspect fill - картинка увеличивается 
    
  Для одновременного открытия storyboard/view - editor options - assistant. Для связыывания элемента в коде ПКМ от элемента в код, connection - outlet. Если надо     сделать функции к кнопке, то connection - action. Переименовывать элементы через refactor - rename. 
  
  Для выбора картинок в коде можно использовать #imageLiteral(resourceName: "filename").
  Для рандомизации выбора значения в массиве предлагается использовать Int.random(in: range), но можно использовать и встроенную функцию массива randomElement().
  Свойства элементов в коде, так же можно подсматривать в инспекторе.
# Раздел 6: Auto Layout and Responsive UIs
Constraints
  leading - левая граница
  trailing - правая граница
  Для того, чтобы растянуть background для констрэйнтов в secondItem указываем superview вместо safeArea/
  Выравнивание задаем через меню - align
  Элементы можно помещать в другие view. И уже выравнивать элементы относительно их. Существуют stacks в которые можно складывать элементы и уже их настраивать.
  В случае если задается фиксированный размер, необходимо указать в настройках greater than or equal, чтобы xcode не ругался
  
