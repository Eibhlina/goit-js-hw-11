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


