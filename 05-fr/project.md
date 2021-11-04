# System aukcyjny

## Wprowadzenie

Specyfikacja wymagań funkcjonalnych w ramach informatyzacji procesu sprzedaży produktów w oparciu o mechanizm aukcyjny. 

## Procesy biznesowe

---
<a id="bc1"></a>
### BC1: Sprzedaż aukcyjna 

**Aktorzy:** [Sprzedający](#ac1), [Kupujący](#ac2)

**Opis:** Proces biznesowy opisujący sprzedaż za pomocą mechanizmu aukcyjnego. |

**Scenariusz główny:**
1. [Sprzedający](#ac1) wystawia produkt na aukcję. ([UC1](#uc1)) ([UC2](#uc2))
2. [Kupujący](#ac2) oferuje kwotę za produkt wyższą od aktualnie najwyższej oferty. ([BR1](#br1)) ([UC3](#uc3))
3. [Kupujący](#ac2) wygrywa aukcję ([BR2](#br2)) ([UC4](#uc4))
4. [Kupujący](#ac2) przekazuje należność Sprzedającemu. ([UC6](#uc6))
5. [Sprzedający](#ac1) przekazuje produkt Kupującemu. ([UC7](#uc7))

**Scenariusze alternatywne:** 

2.A. Oferta Kupującego została przebita, a [Kupujący](#ac2) pragnie przebić aktualnie najwyższą ofertę. ([UC3](#uc3))
* 2.A.1. Przejdź do kroku 2.

3.A. Czas aukcji upłynął i [Kupujący](#ac2) przegrał aukcję. ([BR2](#br2)) ([UC5](#uc5))
* 3.A.1. Koniec przypadku użycia.

---

## Aktorzy

<a id="ac1"></a>
### AC1: Sprzedający

Osoba oferująca towar na aukcji.

<a id="ac2"></a>
### AC2: Kupujący

Osoba chcąca zakupić produkt na aukcji.


## Przypadki użycia poziomu użytkownika

### Aktorzy i ich cele

[Sprzedający](#ac1):
* [UC1](#uc1): Wystawienia produktu na aukcję
* ...

[Kupujący](#ac2)
* [UC2](#uc2): Dołączenie do aukcji
* [UC3](#uc3): Przebicie dotychczasowej oferty
* [UC6](#uc6): Przekazanie środków
* [UC7](#uc7): Potwierdzenie otrzymania przedmiotu
* ...

---
<a id="uc1"></a>
### UC1: Wystawienia produktu na aukcję

**Aktorzy:** [Sprzedający](#ac1)

**Scenariusz główny:**
1. [Sprzedający](#ac1) zgłasza do systemu chęć wystawienia produktu na aukcję.
2. System prosi o podanie danych produktu i ceny wywoławczej.
3. [Sprzedający](#ac1) podaje dane produktu oraz cenę wywoławczą.
4. System weryfikuje poprawność danych.
5. System informuje o pomyślnym wystawieniu produktu na aukcję.

**Scenariusze alternatywne:** 

4.A. Podano niepoprawne lub niekompletne dane produktu.
* 4.A.1. System informuje o błędnie podanych danych.
* 4.A.2. Przejdź do kroku 2.

---

<a id="uc2"></a>
### UC2: Dołączenie do aukcji

**Aktorzy:** [Kupujący](#ac2)

**Scenariusz główny:**
1. [Kupujący](#ac2) zgłasza chęć dołączenia do aukcji.
2. System prosi o podanie danych aukcji i danych [Kupującego](#ac2).
3. [Kupujący](#ac2) podaje dane aukcji i swoje dane.
4. System weryfikuje poprawność danych.
4. System informuje o poprawnym dołączeniu do aukcji.

**Scenariusze alternatywne:** 

4.A. Podano niepoprawne lub niekompletne dane.
* 4.A.1. System informuje o błędnie podanych danych.
* 4.A.2. Prejdź do kroku 2.

---

<a id="uc3"></a>
### UC3: Przebicie dotychczasowej oferty

**Aktorzy:** [Sprzedający](#ac1), [Kupujący](#ac2)

**Scenariusz główny:**
1. [Kupujący](#ac2) prosi o aktualnie najwyższą ofertę.
2. System podaje [kupującemu](#ac2) aktualnie najwyższą ofertę.
3. [Kupujący](#ac2) wyraża chęć przebicia oferty.
4. System prosi [kupującego](#ac2) o podanie nowej oferty.
5. [Kupujący](#ac2) podje nową ofertę.
6. System weryfikuje nową ofertę.
7. System informuje [kupującego](#ac2) o poprawnym przebiciu oferty.
8. System informuje [sprzedającego](#ac1) o nowej ofercie.
9. System informuje [kupującego](#ac2), którego oferta została przebita o nowej ofercie.

**Scenariusze alternatywne:** 

6.A. System informuje o zbyt małej kwocie.
* 6.A.1. Przejdź do kroku 4.

---

<a id="uc4"></a>
### UC4: Ogłoszenie wygranej

**Aktorzy:** [Sprzedający](#ac1), [Kupujący](#ac2)

**Scenariusz główny:**
1. System informuje [kupującego](#ac2), którego oferta była najwyższa, o wygranej.
2. System informuje [sprzedającego](#ac1) o zakończeniu aukcji i wskazuje zwycięzce.

---

<a id="uc5"></a>
### UC5: Ogłoszenie zakończenia aukcji

**Aktorzy:** [Sprzedający](#ac1), [Kupujący](#ac2)

**Scenariusz główny:**
1. System informuje [kupujących](#ac2) o zakończeniu aukcji.
2. System informuje [sprzedającego](#ac1) o zakończeniu aukcji.

---

<a id="uc6"></a>
### UC6: Przekazanie środków

**Aktorzy:** [Sprzedający](#ac1), [Kupujący](#ac2)

**Scenariusz główny:**
1. [Kupujący](#ac2) zgłasza chęć zapłacenia za produkt.
2. System prosi [kupującego](#ac2) o wybranie formy płatności.
3. [Kupujący](#ac2) wybiera system płatności.
4. System przekierowuje [kupującego](#ac2) do wybranego systemu płatności.
5. [Kupujący](#ac2) dokonuje płatności w zewnętrznym systemie.
6. System oczekuje na zakończnie płatności.
7. System informuje [kupującego](#ac2) o poprawnym zakończeniu płatności.
8. System informuje [sprzedającego](#ac1) o opłaceniu produktu.

**Scenariusze alternatywne:** 

6.A. System informuje o błędzie płatności.
* 6.A.1. Przejdź do kroku 2.

---

<a id="uc7"></a>
### UC7: Potwierdzenie otrzymania przedmiotu

**Aktorzy:** [Sprzedający](#ac1), [Kupujący](#ac2), ...

**Scenariusz główny:**
1. ...

**Scenariusze alternatywne:** 

1.A. ...
* 4.A.1. ...

---

## Obiekty biznesowe (inaczej obiekty dziedzinowe lub informatycjne)

### BO1: Aukcja

Aukcja jest formą zawierania transakcji kupna-sprzedaży, w której Sprzedający określa cenę wywoławczą produktu, natomiast Kupujący mogą oferować własną ofertę zakupu każdorazowo proponując kwotę wyższą od aktualnie oferowanej kwoty. Aukcja kończy się po upływie określonego czasu. Jeśli złożona została co najmniej jedna oferta zakupy produkt nabywa ten Kupujący, który zaproponował najwyższą kwotę. 

### BO2: Produkt

Fizyczny lub cyfrowy obiekt, który ma zostać sprzedany w ramach aukcji.

## Reguły biznesowe

<a id="br1"></a>
### BR1: Złożenie oferty

Złożenie oferty wymaga zaproponowania kwoty wyższej niż aktualnie oferowana o minimum 1,00 PLN.


<a id="br2"></a>
### BR2: Rozstrzygnięcie aukcji

Aukcję wygrywa ten z [Kupujący](#ac2)ch, który w momencie jej zakończenia (upłynięcia czasu) złożył najwyższą ofertę.

## Macierz CRUDL


| Przypadek użycia                                  | Aukcja | Produkt | ... |
| ------------------------------------------------- | ------ | ------- | --- |
| UC1: Wystawienia produktu na aukcję               |    C   |    C    | ... |
| ???                                               |  ...   |  ...    | ... |

