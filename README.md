Wstęp

Przez ostatni tydzień poznałeś podstawy programowania obiektowego w Pythonie i podstawy SQL'a. Dowiedziałeś się ponadto, jak korzystać z baz danych przy użyciu Pythona. Pora usystematyzować zdobytą wiedzę i przećwiczyć ją w praktyce. Celem warsztatu jest poznanie sposobu integracji baz danych z programowaniem obiektowym. Można to zrobić na wiele różnych sposobów.

Najpopularniejsze wzorce projektowe rozwiązujące ten problem to:

    Row Data Gateway,
    ActiveRecord,
    DataMapper.

Podczas warsztatu będziemy implementować wzorzec Active Record. Opis tego wzorca znajdziesz w osobnym artykule.
Co będzie do zrobienia?

W trakcie warsztatu stworzysz prosty serwer komunikatów. Będzie się on składał z czterech części:

    skrypt budujący naszą bazę danych,
    biblioteka do zarządzania bazą danych,
    aplikacja do zarządzania użytkownikami,
    aplikacja do wysyłania wiadomości.

Poznasz również, w jaki sposób przechowywane są hasła w bazie danych. Do projektu dołączyliśmy bibliotekę do obsługi haseł. Omówimy ją dokładnie w osobnym artykule.

Omówmy teraz każdą z czterech części projektu.
Skrypt budujący bazę danych

Prosty skrypt tworzący bazę danych i tabele. Powinien być idempotentny.

    Idempotentność – właściwość pewnych operacji, która pozwala na ich wielokrotne stosowanie bez zmiany wyniku. Źródło: https://pl.wikipedia.org/wiki/Idempotentno%C5%9B%C4%87

W praktyce oznacza to, że wielokrotne wywołanie skryptu powinno przynosić ten sam efekt. Powinien działać, niezależnie od tego, czy mamy już utworzoną bazę danych, czy nie. Podobnie powinien się zachować, niezależnie od tego, czy w bazie danych są jakieś tabele, czy nie. Nie powinien usuwać danych, jeśli jakieś znajdują się w bazie.
Biblioteka do zarządzania bazą danych

Będzie to zbiór klas służący do zarządzania tabelami w bazie danych. Wykorzystamy tutaj wspomniany wcześniej wzorzec projektowy Active Record. Poznasz go dokładnie z następnego artykułu.
Aplikacja do zarządzania użytkownikami

Prosta aplikacja konsolowa, do zarządzania użytkownikami. Powinna obsługiwać takie zadania, jak:

    listowanie użytkowników,
    tworzenie nowego użytkownika,
    zmiana hasła użytkownika,
    usuwanie użytkownika.

Aplikacja powinna obsługiwać parametry, przekazywane do niej z poziomu konsoli. Wykorzystamy do tego bibliotekę argparse. Opis podstawowych funkcjonalności tej biblioteki znajdziesz w osobnym artykule.
Aplikacja do wysyłania wiadomości

Kolejna aplikacja konsolowa, umożliwiająca przesyłanie wiadomości między użytkownikami. Powinna implementować takie funkcjonalności, jak:

    wypisanie wszystkich komunikatów wysłanych do użytkownika,
    wysłanie wiadomości.

Ponadto powinna sprawdzać, czy podany użytkownik istnieje i czy hasło jest poprawne.

Podobnie, jak w przypadku aplikacji do zarządzania użytkownika, będziemy obsługiwać hasła, korzystając z biblioteki argparse.
