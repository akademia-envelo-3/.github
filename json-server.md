## Mockowanie bazy danych do testów

[Powrót do README projektu](./profile/README.md)

Wymagania:
1. Zainstalowany Node.js wersja LTS https://nodejs.dev/en/download/ razem z npm
2. Po zainstalowaniu sprawdź czy masz dostęp do `Node` oraz `npm` z wiersza poleceń
![image](https://user-images.githubusercontent.com/100217956/214230600-b4f1f636-a45a-4c53-83f5-42fcfa083c43.png)
3. By uruchomić bazę danych musisz mieć zmockowanego `json` dostarczego przed zespól wytwórczym, najcześciej będzie to plik `db.json`
4. Za pomocą polecania `npx json-server db.json` (musisz być w folderze gdzie znajduje się plik db.json, jeśli nie jesteś musisz wskazać ten plik np. `npx json-server ./mocks/meetek/db-1.0.5.json`. Najważniejsze to wskazać prawidłowy plik, których chcesz użyć jako Twoja baza danych.
5. Gdy uruchamiasz te polecenie `npx json-server` zostaniesz zapytany czy chcesz zainstalować tę zależność na swoim komputerze, wybierz odpowiedni komunikat.
6. Jeśli masz dostarczy prawidłowy plik powinno pokazać Ci się takie okienko z informacją o tym, że twój backend jest dostępny pod adresem `http://localhost:3000` wraz z dostępnymi endpointami.

![image](https://user-images.githubusercontent.com/100217956/214231823-d2be35ce-8f0e-42d7-aa19-fe7c3cb190f4.png)

Powyższy komunikat jest dostępny dla bazy o kształcie:
```json
{
  "pokemons": [{ "id": 1, "name": "Charmander", "powers": [] }],
  "characters": [
    {
      "id": 1,
      "name": "Ash",
      "pokemonsIds": [1]
    }
  ]
}
```

Jeśli chcesz odnieść się konkretnego zasobu możesz to zrobić wskazując odpowiednie `id` np. `http://localhost:3000/characters/1` zwróci nam zasób z tabeli `characters` gdzie `id` to `1`