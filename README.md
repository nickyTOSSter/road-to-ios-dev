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
  
# Раздел 7: Using and Understanding Apple Documentation
Одну функцию можно подключать к нескольким кнопкам. От круга в коде напротив объявления процедуры тянем к нужной кнопке.
Ctrl + I - reindent

Как решать проблемы с которыми ранее не сталкивался:
1. Гуглим "Что надо сделать - Swift - StackOverflow"
2. Попали на stackoverflow - проверяем релевантность вопроса нашему, смотрим лучшие 3 ответа
3. Переносим код пытаемся запустить без ошибок в нашем приложении
4. Ищем в документации и изучаем, как это работает
5. Подгоняем код под работу нашего приложения, что-то добавляем, убираем лишнее

AVFoundation -
AVAudioPlayer - 
Bundle - 
DispatchQueue -

# Раздел 8: Intermediate Swift Programming - Control Flow and Optionals
Для того чтобы текс влезал полностью настраивается свойство Autoshrink. 
В кнопки лучше не добавлять изображения из-за сложности настройки. Лучше накрыть их картинкой.
Опциональный тип Type? этой некий составной тип который может принимать значения типа Type и nil
Для насильного приведения опционального типа в не опциональный тип используется ! делать так крайне не рекомендуется, т.к. может отсутствовать значение и программа ляжет. Один из способов безопасной проверки проверит на != nil

Timer.sheduledTimer - 
# Раздел 9: iOS App Design Patterns and Code Structuring
struct - value type, по умолчанию есть инициализаторы, при создании собственного инициализатора инициализаторы по умолчанию удаляются, должны быть инициализированы все свойства либо через init либо значением по умолчанию, для функций меняющих структуру нужен префикс mutating. Объекты константы не могут менять свои свойства
UIColor.clear - очистить цвет/цвет по умолчанию
Pattern MVC
Model - содержит данные и логику
View - это вьюшка
Controller - ViewController, должен быть только код по работе с элементами вьюшки. Обработать нажатие кнопки, изменить цвет и т.п. Передает данные в модель, вызывает методы модели.
# Раздел 11: Advanced Swift Programming - Classes, Inheritance & Advanced Optionals
Округление при выводе String(format: "%.2f", Value) - 2f - количество знаков после запятой
Для классов обязательна процедура инициализации, если не все параметры заданы по умолчанию. Классы referenceType. Не требуется mutating. Объекты константы могут менять свои свойства
UIViewController - 
Для показа другого view используем команду present текущего view. В него передаем экзмпляр класса необходимого для отражения view. Параметры передаем через свойства второго view.
Контроллеры для новых view создаются через Cocoa Touch Class. Затем созданный класс нужно выбрать в свойствах сцены
Переходы segue. От одного класса тянемся к другому создаем segue. Задаем идентификатор. Вызвать переход методом performSegue. выполнить предварительную настройку в переопределенном методе prepare. В этом методе проверяем идентификатор (segue.identifier). Затем получаем view из segue.destination. View даункастим до нашего класса as! имя_класса_view. И уже затем можно передавать параметры
Для работы с опциональными типами используем: 
  Optional binding - (if let safeOptional = optional { safeOptional})
  nil coalescing operator - (optional ?? defaultValue)
  optional chaining - (optionalObject?.property)
# Раздел 13: Networking, JSON Parsing, APIs and Core Location
Системные цвета поддерживают темную тему автоматически. 
Создание своих цветов светлой/темной темы - в assets добавить новый цвет - выбрать цвет темы по умолчанию и светлой темы - выбрать свет темной темы - задать наименование - выбрать по данному наименованию во view
Для картинок можно использовать pdf. При этом надо установить флаг preserve vector data, scales - single scale. Чтобы можно было менять в зависимости от темы устанавливаем свойстве appearances.
Для работы с UITextField существует протокол UITextFieldDelegate. Этот протокол обеспечивает процедурами на разные события ввод, окончание редактирования и т.д.
Protocol - набор правил для классов и структур (требуется углубиться)
Паттерн Delegate - углубиться:
  protocol ProtocolName {
    func protocolFunc()
  }
  
  class Handler {
    var delegate: ProtocolName?
    delegate.protocolFunc()
  }
  
  class MyClass: ProtocolName {
    var handler = Handler()
    handler.delegate = self
    
    func protocolFunc() {
      // func code
    }
  }
networking - углубиться:
  1. Создать URL - URL(string: urlString)
  2. Создать URLSession - URLSession(configuration: .default)
  3. Дать сессии задание - session.dataTask(with: url, completionHandler: handle(data:response:error:))
  4. Запустить задание - task.resume  
        
    if let url = URL(string: urlString) {
      
      // 2. Create URLSession
      let session = URLSession(configuration: .default)
      
      // 3. Give the session a task
      //let task = session.dataTask(with: url, completionHandler: handle(data:response:error:))
      let task = session.dataTask(with: url) {
        (data: Data?, response: URLResponse?, error: Error?) in
        if error != nil {
          print(error!)
          return
        }
        
        if let safeData = data {
          let dataString = String(data: safeData, encoding: .utf8)
          print(dataString)
        }
      }
      // 4. Start the task
      task.resume()
    }

closures - углубиться, map, reduce, filter
В замыканиях в случае если вызывается функция этого же класса надо прописывать self
При чтении JSON структура должна соответствовать протоколу Decodable
Чтение JSON:
    let decoder = JSONDecoder()
    do {
      let decodedData = try decoder.decode(WeatherData.self, from: weatherData)
    } catch {
      print(error)
    }
При создании модели для декодирования вложенные данные берутся из структур
  struct WeatherData: Decodable {
    let name: String
    let main: Main
    let weather: [Weather]
  }

  struct Main: Decodable {
    let temp: Double
  }

  struct Weather: Decodable {
    let description: String
  }

condition property - всегда var, значение вычисляется в фигурных скобках в момент вызова свойства
  var temperatureString: String {
      return String(format: "%.1f", temperature)
  } 

Протокол создается в том же файле, что и класс который будет его использовать
Для функции делегата первым параметром необходимо передавать класс, который использует данную функцию
func didUpdateWeather(_ weatherManager: WeatherManager, weather: WeatherModel)
struct WeatherManager {
 var delegate: WeatherManagerDelegate?
 delegate?.didUpdateWeather(self, weather: weather)
}
Для обновления интерфейса из completionHandler надо перейти в основной поток с помощью
DispatchQueue.main.async {} и провести обновление в нем

sf симвлоы указываются через UIImage.image(systemName:)

extension SomeType: SomeProtocol {} при расширении класса с протоколом протокол у класса убрать
Пакет CoreLocation используется для геолокации. Необходимо использовать менеджер let locationManager = CLLocationManager(). При запуске запросить разрешение на использование данны о локации пользователя locationManager.requestWhenInUseAuthorization(). В info.plist настроить сообщение зачем нужна информация о локации
