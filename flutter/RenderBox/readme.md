```dart
import 'dart:ui' as ui;

void main() {
  final window = ui.window;

  window.onDrawFrame = () {
    final recorder = ui.PictureRecorder();
    final canvas = ui.Canvas(recorder);

    // Рисуем красный круг
    final paint = ui.Paint()..color = ui.Color.fromARGB(255, 255, 0, 0); // Красный цвет
    final center = ui.Offset(window.physicalSize.width / 2, window.physicalSize.height / 2); // Центр экрана
    final radius = 100.0; // Радиус круга
    canvas.drawCircle(center, radius, paint);

    final picture = recorder.endRecording();
    final sceneBuilder = ui.SceneBuilder();
    sceneBuilder.addPicture(ui.Offset.zero, picture);
    window.render(sceneBuilder.build());
  };

  window.scheduleFrame();
}
```

# Отрисовка круга с использованием `dart:ui`

Этот код демонстрирует, как работать напрямую с низкоуровневым API `dart:ui` для рендеринга графики в Flutter-приложении без использования стандартных виджетов.

## Описание

Программа создает красный круг в центре экрана, используя `dart:ui`. Отрисовка выполняется с помощью `PictureRecorder` и `Canvas`, а затем результат рендерится в `SceneBuilder`.

## Как работает код

1. Получаем окно (`ui.window`).
2. Устанавливаем обработчик `onDrawFrame`, который будет вызываться при обновлении кадра.
3. Создаем `PictureRecorder` и `Canvas` для рисования.
4. Определяем кисть (`Paint`) с красным цветом.
5. Определяем центр экрана и рисуем круг радиусом `100.0`.
6. Завершаем запись рисунка и добавляем его в сцену (`SceneBuilder`).
7. Отображаем отрисованную сцену в окне.
8. Запрашиваем обновление кадра вызовом `scheduleFrame()`.

## Запуск

Этот код может быть выполнен только в окружении Flutter, где доступен `dart:ui`. Он предназначен для использования в нативном рендеринге Flutter и не работает в стандартном `main.dart` без настройки соответствующего окружения.

## Примечание

Такой способ рисования используется в сложных графических задачах, например, при создании анимаций, кастомных эффектов или игр, когда стандартные виджеты Flutter не подходят.
