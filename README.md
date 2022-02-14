# Чистый Marlin (2.0.5.3) для Hercules 2018 :ru:

## Уже включенные параметры :wrench:

-  **Прошивка настроена под TMC2209 на экструдере!** (`#define E0_DRIVER_TYPE TMC2209_STANDALONE` и `#define INVERT_E0_DIR true`)
-  `#define LIN_ADVANCE` - **Linear Pressure Control**
-  `#define PID_AUTOTUNE_MENU` — **автокалибровка PID** (экструдера) через **меню**.
-  `#define PIDTEMPBED` — выключите, либо **произведите автокалибровку**
-  `#define THERMAL_PROTECTION_HOTENDS` и `#define THERMAL_PROTECTION_BED`
-  `#define S_CURVE_ACCELERATION`
-  `#define EEPROM_SETTINGS` — теперь все **настройки** (PID's, ускорения, джерки и тд.) **хранятся в памяти** контроллера.
-  `#define ADVANCED_PAUSE_FEATURE` — смена филамента командой M600 (через плагин Cura, например) или через меню.
-  `#define LCD_LANGUAGE en` — мне комфортнее с **английским языком**, можете изменить на `ru`.
-  `#define ADAPTIVE_STEP_SMOOTHING`
-  `#define LCD_SET_PROGRESS_MANUALLY` — позволяет выводить **прогресс** печати с [OctoPrint](https://github.com/OctoPrint/OctoPrint) *(необходим еще плагин)* на экран принтера.
-  `#define POWER_LOSS_RECOVERY` —**еще не проверял!**
- ~~возможно что-то еще :sweat_smile:~~

## Установка :computer:

-  **PlatformIO**  *(тогда вы знаете что делать*)
-  **Arduino IDE:**

1. Скачайте [архив](https://github.com/celgus/Marlin-H18/archive/master.zip).
2.  **Обязательно** распакуйте содержимое архива в папу **"Marlin"**!
3. Откройте **"Marlin.ino"**.
4. Выберите "*Инструменты*" :arrow_right: "*Управлять библиотеками*" :arrow_right: необходимо найти и установить **U8glib** и **LiquidCrystal**.
5. Выберите "*Инструменты*" :arrow_right: "*Плата*" :arrow_right: "**Arduino Mega or Arduino Mega 2560**".
6. Выберите "*Инструменты*" :arrow_right: "*Процессор*" :arrow_right: "**ATmega2560**".
7. Выберите "*Скетч*" :arrow_right: "**Загрузка**"
8.  **Готово! :white_check_mark:**
> Arduino IDE может долго компилировать прошивку, не закрывайте окно и не отключайте плату от ПК.
9. Сбросьте содержимое EEPROM в дефолтные значения командой M502 и сохраните в EPPROM командой M500.
11. Если на LCD панели после загрузки будут артефакты, необходимо изменить дефолтные тайминги:

```
#define ST7920_DELAY_1 DELAY_NS(50) // After CLK LOW
#define ST7920_DELAY_2 DELAY_NS(150) // After DAT
#define ST7920_DELAY_3 DELAY_NS(50) // After CLK HIGH
```

Этот код нужно добавить в конец Configuration.h
Подробнее можно прочитать тут https://marlinfw.org/docs/basics/troubleshooting.html 

*По любым вопросам можете обращаться в Telegram  **@celgus***  
