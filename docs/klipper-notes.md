# Мои заметки по клипперу

[Бекап моей текущей конфигурации](https://github.com/thghca/klipper_config)
[Гайды по конфигурации](https://github.com/AndrewEllis93/Print-Tuning-Guide)

## Модули

### [Klipper-Stable-Z-Home](https://github.com/matthewlloyd/Klipper-Stable-Z-Home)

Модуль позволяет повторять хоуминг оси Z пока положение нуля не стабилизируется.
Полезно со щупом (bltouch). Можно дождатся пока кровать завершит температурное расширение.

## Программы

### [klipper-hotkeypad](https://github.com/thghca/klipper-hotkeypad)

Скрипт для использования обычной usb клавиатуры в качестве макропада.

## Обновление до python3
```
sudo service klipper stop
sudo service moonraker stop
mv ~/klippy-env ~/klippy-env-27
virtualenv -p python3 ~/klippy-env
~/klippy-env/bin/pip install -r ~/klipper/scripts/klippy-requirements.txt
sudo service klipper start
sudo service moonraker start
```

## Фрагменты макросов

### Лимиты принтера

```
{% set X_MAX = printer.toolhead.axis_maximum.x|default(100)|float %}
{% set Y_MAX = printer.toolhead.axis_maximum.y|default(100)|float %}
{% set Z_MAX = printer.toolhead.axis_maximum.z|default(100)|float %}
```
