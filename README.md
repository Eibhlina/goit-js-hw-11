# Zadanie — Wyszukiwanie obrazów

Utwórz aplikację do wyszukiwania obrazów według słów kluczowych i wyświetlania ich w galerii. Zaprojektuj elementy interfejsu zgodnie z układem.


## Formularz wyszukiwania

Formularz wyszukiwania jest zawarty w dokumencie HTML. Użytkownik będzie wprowadzał tekst w polu tekstowym do wyszukiwania, a po przesłaniu formularza nastąpi wysłanie żądania HTTP z tym tekstem.


## Żądania HTTP

Korzystaj z publicznego API usługi Pixabay dla backendu. Zarejestruj się, uzyskaj unikalny klucz dostępu i zapoznaj się z dokumentacją.

Lista parametrów ciągu żądania, które trzeba określić:

* key — Twój unikalny klucz dostępu do API.
* q — słowo do wyszukania. To, co wprowadzi użytkownik.
* image_type — typ obrazu. Potrzebujesz tylko zdjęć, więc ustaw wartość photo.
* orientation — orientacja zdjęcia. Ustaw wartość horizontal.
* safesearch — filtrowanie według wieku. Ustaw wartość true.

Odpowiedź będzie zawierać obiekt z kilkoma właściwościami, z których jedna będzie zawierać tablicę obrazów spełniających kryteria parametrów wyszukiwania.

Jeśli backend zwróci pustą tablicę, oznacza to, że nie znaleziono nic odpowiedniego. W takim przypadku należy wyświetlić komunikat z tekstem „Sorry, there are no images matching your search query. Please try again!” („Przepraszamy, nie ma obrazów zgodnych z wyszukiwaniem. Spróbuj ponownie!”) . Do wyświetlania komunikatów użyj biblioteki iziToast.

Aby dołączyć kod CSS biblioteki do projektu, należy dodać kolejny import, oprócz tego opisanego w dokumentacji.


## Galeria i karty obrazów

Element galerii (lista podobnych elementów) jest zawarty w dokumencie HTML. Należy dodawać do niego znaczniki kart obrazów po żądaniach HTTP.

Każdy obraz jest opisany przez obiekt, z którego interesują nas tylko następujące właściwości:

* webformatURL — link do małego obrazka, aby wyświetlić listę kart w galerii.
* largeImageURL — link do dużego obrazu dla okna modalnego.
* tags — tekst opisujący obraz. Nadaje się do atrybutu alt.
* likes — liczba polubień.
* views — liczba wyświetleń.
* comments — liczba komentarzy.
* downloads — liczba pobrań.

Przed wyszukaniem nowego słowa kluczowego należy całkowicie oczyszczać zawartość galerii, aby nie mieszać wyników zapytań.

## Biblioteka SimpleLightbox

Dodaj wyświetlanie dużej wersji obrazu za pomocą biblioteki SimpleLightbox, aby utworzyć pełnoprawną galerię.

Aby dołączyć kod CSS biblioteki do projektu, należy dodać jeszcze jeden import, oprócz tego opisanego w dokumentacji.

* W znacznikach należy zawinąć każdą kartę obrazu w link, jak opisano w dokumentacji w sekcji Markup.
* Biblioteka zawiera metodę [refresh()](<https://github.com/andreknieriem/simplelightbox#public-methods>), która musi być wywoływana przy każdym dodaniu nowych elementów do galerii.


## Wskaźnik pobierania

Dodaj element, który informuje użytkownika, że trwa proces pobierania obrazów z backendu. Wskaźnik pobierania powinien pojawić się tuż przed rozpoczęciem żądania HTTP i zniknąć po jego zakończeniu.













# Vanilla App Template

Цей проект було створено за допомогою Vite. Для знайомства та налаштування
додаткових можливостей [звернись до документації](https://vitejs.dev/).

## Створення репозиторію за шаблоном

Використовуй цей репозиторій організації GoIT як шаблон для створення
репозиторію свого проекту. Для цього натисни на кнопку `«Use this template»` і
обери опцію `«Create a new repository»`, як показано на зображенні.

![Creating repo from a template step 1](./assets/template-step-1.png)

На наступному етапі відкриється сторінка створення нового репозиторію. Заповни
поле його імені, переконайся, що репозиторій публічний, після чого натисни
кнопку `«Create repository from template»`.

![Creating repo from a template step 2](./assets/template-step-2.png)

Після того, як репозиторій буде створено, необхідно перейти в налаштування
створеного репозиторію на вкладку `Settings` > `Actions` > `General` як показано
на зображенні.

![Settings GitHub Actions permissions step 1](./assets/gh-actions-perm-1.png)

Проскроливши сторінку до самого кінця, в секції `«Workflow permissions»` обери
опцію `«Read and write permissions»` і постав галочку в чекбоксі. Це необхідно
для автоматизації процесу деплою проекту.

![Settings GitHub Actions permissions step 2](./assets/gh-actions-perm-2.png)

Тепер у тебе є особистий репозиторій проекту, зі структурою файлів та папок
репозиторію-шаблону. Далі працюй з ним, як з будь-яким іншим особистим
репозиторієм, клонуй його собі на комп'ютер, пиши код, роби коміти та відправляй
їх на GitHub.

## Підготовка до роботи

1. Переконайся, що на комп'ютері встановлено LTS-версію Node.js.
   [Скачай та встанови](https://nodejs.org/en/) її якщо необхідно.
2. Встанови базові залежності проекту в терміналі командою `npm install`.
3. Запусти режим розробки, виконавши в терміналі команду `npm run dev`.
4. Перейдіть у браузері за адресою
   [http://localhost:5173](http://localhost:5173). Ця сторінка буде автоматично
   перезавантажуватись після збереження змін у файли проекту.

## Файли і папки

- Файли розмітки компонентів сторінки повинні лежати в папці `src/partials` та
  імпортуватись до файлу `index.html`. Наприклад, файл з розміткою хедера
  `header.html` створюємо у папці `partials` та імпортуємо в `index.html`.
- Файли стилів повинні лежати в папці `src/css` та імпортуватись до HTML-файлів
  сторінок. Наприклад, для `index.html` файл стилів називається `index.css`.
- Зображення додавай до папки `src/img`. Збирач оптимізує їх, але тільки при
  деплої продакшн версії проекту. Все це відбувається у хмарі, щоб не
  навантажувати твій комп'ютер, тому що на слабких компʼютерах це може зайняти
  багато часу.

## Деплой

Продакшн версія проекту буде автоматично збиратися та деплоїтись на GitHub
Pages, у гілку `gh-pages`, щоразу, коли оновлюється гілка `main`. Наприклад,
після прямого пуша або прийнятого пул-реквесту. Для цього необхідно у файлі
`package.json` змінити значення прапора `--base=/<REPO>/`, для команди `build`,
замінивши `<REPO>` на назву свого репозиторію, та відправити зміни на GitHub.

```json
"build": "vite build --base=/<REPO>/",
```

Далі необхідно зайти в налаштування GitHub-репозиторію (`Settings` > `Pages`) та
виставити роздачу продакшн версії файлів з папки `/root` гілки `gh-pages`, якщо
це не було зроблено автоматично.

![GitHub Pages settings](./assets/repo-settings.png)

### Статус деплою

Статус деплою крайнього коміту відображається іконкою біля його ідентифікатора.

- **Жовтий колір** - виконується збірка та деплой проекту.
- **Зелений колір** - деплой завершився успішно.
- **Червоний колір** - під час лінтингу, збірки чи деплою сталася помилка.

Більш детальну інформацію про статус можна переглянути натиснувши на іконку, і в
вікні, що випадає, перейти за посиланням `Details`.

![Deployment status](./assets/deploy-status.png)

### Жива сторінка

Через якийсь час, зазвичай кілька хвилин, живу сторінку можна буде подивитися за
адресою, вказаною на вкладці `Settings` > `Pages` в налаштуваннях репозиторію.
Наприклад, ось посилання на живу версію для цього репозиторію

[https://goitacademy.github.io/vanilla-app-template/](https://goitacademy.github.io/vanilla-app-template/).

Якщо відкриється порожня сторінка, переконайся, що у вкладці `Console` немає
помилок пов'язаних з неправильними шляхами до CSS та JS файлів проекту
(**404**). Швидше за все у тебе неправильне значення прапора `--base` для
команди `build` у файлі `package.json`.

## Як це працює

![How it works](./assets/how-it-works.png)

1. Після кожного пуша у гілку `main` GitHub-репозиторію, запускається
   спеціальний скрипт (GitHub Action) із файлу `.github/workflows/deploy.yml`.
2. Усі файли репозиторію копіюються на сервер, де проект ініціалізується та
   проходить лінтинг та збірку перед деплоєм.
3. Якщо всі кроки пройшли успішно, зібрана продакшн версія файлів проекту
   відправляється у гілку `gh-pages`. В іншому випадку, у лозі виконання скрипта
   буде вказано в чому проблема.
