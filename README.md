Question: What issues prevent us from using storyboards in real projects?
-
Answer:
  ~ Firstly, the main issue is using constraints - we cant control auto layout constraints. Secondly, its hard to use any architecture(design) patterns
    so it can make code harder to read and maintain.
    ```
    * Во-первых, основная проблема заключается в использовании констрейнтов: мы не можем контролировать автоматическое расположение констрейнтов.
    Во-вторых, сложно использовать какие-либо шаблоны архитектуры, поэтому это может затруднить чтение и поддержку кода.
    ```

Question: What does the code on lines 25 and 29 do?
  25. title.translatesAutoresizingMaskIntoConstraints = false
  29. view.addSubview(title)
-
Answer:
  ~ the code on line 25 disables automatic constraints on specific view (here title) and allows us to set our own manually.
    ```
    * код на 25 строчке отключает автоматическое изменение констрейнтов, чтобы мы смогли далее установить собственные для данного view (title).
    ```
  ~ the code on line 29 appears our title as view by adding subview on view(screen)
    ```
    * код на 29 строчке добавляет к нашему исходному view (экрану) заголовок (title)
    ```

Question: What is a safe area layout guide?
-
Answer:
  ~ the safe area is a place on screen where subviews can be placed and they won`t be covered by navigation bars, tab bars,
    toolbars, and other ancestor views. So safe area layout guide reflects this place and if the view is not currently installed
    in a view hierarchy, or is not yet visible onscreen, the layout guide edges are equal to the edges of the view.
    ```
    * safe area — это место на экране, где можно разместить views, и они не будут закрыты панелями навигации, панелями вкладок,
      панели инструментов и др. Таким образом, safe area layout guide отражает это место, и если view
      в настоящее время не установлено в иерархии views, или view еще не видно на экране, края layout guide равны краям view.
    ```


Question: What is [weak self] on line 23 and why it is important?
  23. sliderRed.valueChanged = { [weak self] value in self?.view.backgroundColor = ... }
  -
Answer:
  ~ [weak self] is a construct used in closures that avoids strong reference cycles. In our case it is necessary to avoid leakage
    memory (objects will refer to each other and will not be deleted from memory), and also so that the execution of this code fragment ends
    when a nil value occurs in self. In our case, it is important to avoid nil, since we use value, and without making the reference weak, we can
    get exceptions.
    ```
    * [weak self] - конструкция, используемая в замыканиях, которая позволяет избежать сильных циклов ссылок. Т.е в нашем случае она необходима, чтобы избежать утечки
      памяти (обьекты станут ссылаться друг на друга и не будут освобождены из памяти), а также, чтобы выполнения данного фрагмента кода завершилось
      при возникновении значения nil в self. В нашем же случае важно избежать nil, так как мы впоследствии используем value, и ,не сделав ссылку слабой, мы можем
      получить exeptions.
    ```
    
Question: What does clipsToBounds mean?
 7. stack.clipsToBounds = true
 -
Answer:
  ~ clipToBounds default value is false, so when we make it true it causes subviews to be clipped to the bounds of the view. So clipsToBounds means if the view
  clipped to bounds of (main)view or not.
  ```
  * Значение по умолчанию clipToBounds — false, поэтому, когда мы делаем его истинным, это приводит к тому, что subview обрезаются до границ view.
    Таким образом, clipsToBounds означает, что subview обрезано до границ view или нет.
  ```

Question: What is the valueChanged type? What is Void and what is Double?
11. var valueChanged: ((Double) -> Void)?
-
Answer:
  ~ valueChanged type is ((Double) -> Void)? which means valueChanged is a property that can hold a closure that takes one parameter of type Double and returns 
   no value (void). So it can be optional, it can either be a valid closure or nil. Void is simply an empty tuple, it's used for for functions that return nothing 
   ans Double is a type which can be shown as a floating-point number.
  ```
  * Тип valueChanged ((Double) -> Void)? что означает, что valueChanged — это свойство, которое может содержать замыкание, которое принимает один параметр типа
    Double и возвращает не имеет значения (недействительно). Таким образом, это может быть необязательно, это может быть либо допустимое замыкание, либо ноль.
    Void — это пустой кортеж, он используется для функций, которые ничего не возвращают, а Double — это тип, который представляет собой число с плавающей запятой.
  ```

p.s: Извините, пожайлуста, за мой английский. Добавила описание на русском)
