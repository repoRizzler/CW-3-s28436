# refactoring-example
W tym zadaniu Waszym zadaniem jest modyfikacja kodu aplikacji nazwanej LegacyApp. Zakładamy, że jest to pewna spadkowa aplikacja i chcemy poprawić jakość jej kodu. Chcemy, aby kod w projekcie „LegacyAppConsumer” nie uległ modyfikacji. Innymi słowy kodu w tym projekcie nie możemy modyfikować.
Wszystko w projekcie LegacyApp może być modyfikowane – tak długo dopóki nie powoduje to zmiany interfejsu klas wykorzystywanych w projekcie LegacyAppConsumer. Dodatkowo nie można zmodyfikować klasy UserDataAccess i metody statycznej AddUser. Zakładamy, że w pewnych przyczyn nie możemy modyfikować tej klasy.


# Ulepszenia w kodzie `UserService`

## 🔍 Kluczowe zmiany

### ✅ 1. Wydzielona walidacja danych użytkownika
Przeniesiono walidację do metody `IsValidUserInput`, aby uprościć główną metodę `AddUser`.

- Sprawdzanie, czy imię i nazwisko nie są puste.
- Weryfikacja formatu adresu e-mail.
- Obliczanie wieku użytkownika.

### 🎯 2. Nowa metoda do obliczania wieku
Metoda `CalculateAge` poprawia czytelność i eliminuje powtarzający się kod.

- Ustala wiek na podstawie bieżącej daty.
- Uwzględnia miesiąc i dzień urodzin.

### 👤 3. Oddzielone tworzenie użytkownika
Metoda `CreateUser` upraszcza inicjalizację obiektu `User`.

- Przyjmuje podstawowe dane użytkownika i klienta.
- Zwraca nowy obiekt `User`.

### 💳 4. Ulepszona logika limitu kredytowego
Metoda `AssignCreditLimit` upraszcza proces przypisywania limitu kredytowego.

- **Bardzo ważny klient (`VeryImportantClient`)** → Brak limitu kredytowego.
- **Ważny klient (`ImportantClient`)** → Limit kredytowy podwajany.
- **Zwykły klient** → Limit kredytowy pobierany z usługi.

### 🛠 5. Poprawiona struktura kodu
- Usunięto zbędne zagnieżdżenia.
- Podział na mniejsze, łatwiejsze do testowania metody.
- Lepsza czytelność i zgodność z **Single Responsibility Principle (SRP)**.

---

Dzięki temu kod jest **bardziej przejrzysty, łatwiejszy w utrzymaniu i rozszerzalny**! 🚀  
