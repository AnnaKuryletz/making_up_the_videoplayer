# Документация к HTML-коду видеоплеера

![alt text](image.png)

## Описание
Данный код представляет собой HTML-страницу с видеоплеером, оформленным с использованием CSS и подключаемых скриптов. В плеере предусмотрены кнопки управления: воспроизведение, пауза, регулировка громкости и полноэкранный режим. Также добавлена тень вокруг контейнера с плеером.

Ссылка на проект: [making_up_the_videoplayer](https://annakuryletz.github.io/making_up_the_videoplayer/)

---

## Структура кода

### 1. Заголовок страницы
```html
<title>Пример подключения плеера</title>
<link rel="icon" type="image/png" href="https://dashboard.snapcraft.io/site_media/appmedia/2021/03/external-content.duckduckgo.com.png" />
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" />
<meta charset="utf-8" />
```
**Описание:**
- Заголовок страницы.
- Подключение favicon.
- Подключение Font Awesome для использования иконок.
- Определение кодировки UTF-8.

### 2. CSS-оформление
```css
.shadow {
  box-shadow: 0 0 50px rgb(96, 210, 202);
  display: inline-block;
}
```
**Описание:**
- Добавляет свечение вокруг плеера.

```css
.video-player {
  width: 1000px;
  height: 700px;
  display: flex;
  flex-direction: column;
  background: black;
}
```
**Описание:**
- Основной контейнер видеоплеера.
- Установлена ширина 1000px и высота 700px.
- Элементы внутри организованы в колонку.

```css
.video-container {
  flex-grow: 1;
  background: black;
}
```
**Описание:**
- Контейнер для видео, занимает всё доступное пространство.

```css
.player-controls {
  background: black;
  display: flex;
}
```
**Описание:**
- Контейнер для кнопок управления.

```css
.player-controls button {
  border: none;
  width: 55px;
  height: 55px;
  cursor: pointer;
  color: white;
  background: transparent;
  font-size: 120%;
}
```
**Описание:**
- Оформление кнопок управления.

```css
.spacer {
  flex-grow: 1;
}
```
**Описание:**
- Пустой div, который отталкивает кнопку fullscreen вправо.

---

## 3. Основной HTML-код
```html
<div class="shadow">
  <div class="video-player">
    <div class="video-container"></div>
    <div class="player-controls">
      <button class="play-button"><i class="fa fa-play"></i></button>
      <button class="pause-button"><i class="fa fa-pause"></i></button>
      <button class="volume-button"><i class="fa fa-volume-up"></i></button>
      <button class="mute-button"><i class="fa fa-volume-off"></i></button>
      <div class="spacer"></div>
      <button class="fullscreen-button"><i class="fa fa-arrows-alt"></i></button>
    </div>
  </div>
</div>
```
**Описание:**
- `shadow` — контейнер с тенью.
- `video-player` — главный блок плеера.
- `video-container` — место для видео.
- `player-controls` — кнопки управления:
  - Воспроизведение (`.play-button`).
  - Пауза (`.pause-button`).
  - Увеличение громкости (`.volume-button`).
  - Отключение звука (`.mute-button`).
  - Полноэкранный режим (`.fullscreen-button`).
  - `spacer` отталкивает кнопку fullscreen вправо.

---

## 4. Подключение скриптов
```html
<script src="https://code.jquery.com/jquery-3.4.1.min.js"></script>
<script src="https://unpkg.com/playable@2.10.3/dist/statics/playable.bundle.min.js"></script>
<script src="player.js"></script>
<script type="text/javascript">
  createPlayer({ elementClass: ".video-player" });
</script>
```
**Описание:**
- Подключение jQuery.
- Подключение библиотеки `playable` для работы с видео.
- Подключение `player.js` (внешний файл, содержащий логику плеера).
- Инициализация плеера с классом `.video-player`.

---

## Заключение
Этот код создает видеоплеер с кнопками управления и теневым оформлением. В нём используется `flexbox` для адаптивного расположения элементов, а также `playable.js` для работы с видео. Дополнительные примеры и пояснения можно найти по ссылке: [making_up_the_videoplayer](https://annakuryletz.github.io/making_up_the_videoplayer/).

