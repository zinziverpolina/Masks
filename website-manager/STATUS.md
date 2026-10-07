# Веб-сайт-менеджер — состояние работ

Рабочая память чата «веб-сайт-менеджер» (координирует все чаты по сайту Полины Зинзивер).
Обновлено: 2026-10-05.

## Где что живёт

- Сайт: репозиторий `zinziverpolina/portfolio`, ветка `main`, GitHub Pages.
  - Художественный: `index.html` → https://zinziverpolina.github.io/portfolio/
  - Коммерческий: `commercial.html` (интро-сцена) + `commercial/<slug>.html` (страницы проектов)
  - Скрытые: `commercial/drafts.html`, `commercial/dub.html`, `review/nothing/` (ревью рекламы Nothing)
  - Локальный клон у Полины: `C:\Users\Asus\portfolio-site`
- CV: `zinziverpolina/Polina-CV`.
- Правила Полины: скилл `artist-portfolio` (показывать до публикации, не выдумывать факты, тексты на английском, общение на русском).

## Чаты

| Чат | Где | Зона |
|---|---|---|
| Модели для веб-карточек (`session_01CMhn8xmNXvZ3kt2u46qipb`) | её Windows-ПК | 3D-карточки, страницы проектов, отбор галочками. Скилл `web-model-cards` |
| LOGO ZINZIVER (`session_01RtwP4czy92EKUnwJvdn1NE`) | её Windows-ПК, ComfyUI | 3D-вордмарк «Polina Zinziver» |
| commercial site design | не виден менеджеру (локальный, без Remote Control?) | каркас коммерческого сайта, меню, переходы, HOROSOAPS, Nothing review |

Риск: несколько чатов пушат в один клон и в `main` одновременно — давать каждому свою зону.

## Коммерческий сайт — открытые задачи

1. Virtual Gap Year — ждёт отбора галочками.
2. DUB — нужна правильная папка с файлами.
3. Подтвердить годы/роли/подписи HYPERTRASH, Posters & covers, Hennessy (взяты из имён папок); AquaTM = AQTM?
4. Названия роликов на LOEWE (сейчас подписаны форматами).
5. Сторонние ассеты (колосья, ягоды) на LOEWE Christmas: убрать / подписать / оставить.
6. Squad Monster в SHR; подпись об авторстве моделей.
7. Перепроверить отбор: HYPERTRASH 2024 covers (все 12 видео удалены), Clara (3 из 20), опустевшие группы постеров.
8. Нет шоурила и контактов на коммерческой главной.
9. TGS-анимация для интро не прислана.

## Логотип — открытые задачи

- Ревью 2 (39 вариантов): https://claude.ai/artifact/WJqvCsp7HWF8JayY39gYzy — ждёт отметок.
- Галерея: https://claude.ai/artifact/KFpBsUHKTio4yG12baA3Jm (раунд 9 → №104–133).
- Лицензии шрифтов (Robbery, Saint, Mirabela — не ясно; Kinky — personal & commercial).
- Финал собрать чисто (вектор / C4D), ИИ путает буквы.
- Как логотип встанет в шапку сайта.

## ПОСЛЕДНИЙ ЭТАП: вес сайта (решение Полины — делать в самом конце)

Замер 2026-10-05: сайт без .git ≈ 980 МБ при лимите GitHub Pages 1 ГБ.
- Видео 827 МБ (57 файлов), картинки 82 МБ, 3D-модели 69 МБ (53 GLB).
- Полный список видео: `videos-2026-10-05.csv` (размер, разрешение, длительность, битрейт, страница).

Страницы: LOEWE SS22 195 МБ · LOEWE Christmas 148 · Nina Ricci 109 · HOROSOAPS 93 · HYPERTRASH 90 ·
Posters 87 · художественная (2050) 66 · SHR 59 · Nothing review 48 · Clara 39 · Hennessy 36.

Топ видео: clara-1 33 МБ · posters-v1 30 · hypertrash-v1 30 · horosoaps-v1 29 · posters-v2 29 ·
nothing/phone/hq 24 · loewe-xmas-1 23 · loewe-owl-p 23 · horosoaps-v3 23 · horosoaps-3 22.

План:
1. Пережать все видео: x264 `-preset slow -crf 22..24 -pix_fmt yuv420p -c:a aac -b:a 128k -movflags +faststart`,
   вертикальные LOEWE (до 2250×3000) ограничить 1080 по короткой стороне.
   Тест: clara-1 33→6–8 МБ, loewe-ww-1 20→6–8 МБ, SSIM 0.993. Ожидание: видео ~250 МБ вместо 830.
2. Длинные ролики → Vimeo/YouTube. Полина говорит, что ссылки есть в «первой итерации коммерческого
   портфолио» — в истории репо их НЕТ (там только B Pressure vimeo.com/348256701 и youtu.be/YwgAX1AkGR4,
   оба художественные). Нужен источник от Полины (Slides / Behance / старый сайт).
3. 3D-модели: gltf-transform `optimize --compress meshopt --texture-compress webp --texture-size 1024`.
   Тест: xm-owl 5.2→1.2 МБ, shr-squad-monster 4.3→1.0, lw-peas 3.7→0.6, shr-mouth-arch 3.7→1.0.
   Ожидание: 69 → ~17 МБ. ВНИМАНИЕ: meshopt требует декодер — в three.js (`float-scene.js`, `shr-world.js`)
   добавить `GLTFLoader.setMeshoptDecoder`, model-viewer подхватывает сам. Проверить в браузере каждую карточку.
   Модели сейчас без сжатия геометрии, текстуры PNG/JPEG до 2048².
4. После отбора убрать `review/nothing/` (служебная).
5. Порядок: остановить другие чаты на `commercial/video` и `commercial/models` → собрать локально →
   показать Полине → пуш.

## 2026-10-06 — LOEWE: свободная раскладка в рамках (тест)

- Запрос Полины: на LOEWE небесную сцену (Live Laugh Loewe) убрать вниз страницы; все картинки/видео —
  в рамках как на главной, «выплывают ровно, падают», их можно перетаскивать и оставлять на месте.
- Сделано как тестовая копия, живая `commercial/loewe.html` НЕ тронута:
  `commercial/loewe-test.html` (noindex) + `commercial/scatter.js` + `commercial/scatter.css` (коммит 6158489 в main).
  Карточки падают сверху по очереди с отскоком, плавают, драг → остаются на месте (соседи отодвигаются),
  клик → открывается крупно (видео со звуком), одновременно играют максимум 3 видео. На телефоне: удержать и тянуть.
- Ждём отзыв Полины → потом перенести в `loewe.html` (согласовать с чатом, который ведёт LOEWE sky).

## 2026-10-07 — передача

Знания этого чата оформлены в скилл `website-manager/skill/website-manager/` и переданы чату LOGO ZINZIVER
(сохранить у Полины в `C:\Users\Asus\.claude\skills\website-manager\`). Чат «веб-сайт-менеджер» заархивирован.
