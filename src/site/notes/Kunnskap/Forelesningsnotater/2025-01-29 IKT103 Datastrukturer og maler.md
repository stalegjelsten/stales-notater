---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesningsnotater/2025-01-29 IKT103 Datastrukturer og maler/","title":"2025-01-29 IKT103 Datastrukturer og maler","tags":["forelesning"]}
---


# 2025-01-29 IKT103 Datastrukturer og maler

Foreleser::Christian Auby
Fag:: ikt103
[[Kunnskap/IKT103\|IKT103]]

[[#Video]]
[[#Presentasjon]]

## Datastrukturer
- Å utvikle software handler i stor grad om hvordan vi skal lagre og hente ut data.
- Vi kombinerer simple datatyper for å lage mer komplekse datatyper

### Data vs datatyper vs datastrukturer
- **Data** er variabler og deres innhold.
- **Datatyper** bestemmer hvilke data som kan lagres. For eksempel int, float, student (egendefinert klasse).
- **Datastrukturer** bestemmer hvordan data kan lagres. For eksempel lister, trær, grafer.

### Primitive datatyper
- En datatype som brukes til å bygge opp mer komplekse datatyper
- Eksempler: `int`, `float`, `char`, `bool`
- *Ustrukturerte, primitive datatyper unngås der det er mulig*.

### Sammensatte datatyper
- Bruker eksisterende primitive eller sammensatte datatyper for å skape en ny datatype
- Blir ofte sammenheng mellom hvordan en database ser ut og hvordan datatypene ser ut

#### Plain old data
- *POD (Plain old data)*: Hvis en sammensatt datatype ikke har noen statiske medlemmer
	- En statisk medlemsvariabel er felles for alle instanser
- Ble opprinnelig brukt som begrep for datatyper som kun bruktes for å holde data

Eksempel `struct` med simple datatyper og ingen statiske medlemmer som er plain old data.
```c
struct Account
{
	char ownerName[100];
	int accountNumber;
	float accountBalance;
}
```

### Abstrakte datatyper (ADT)
- Endrer hvordan dataene aksesseres
- Lager logiske begrensninger i koden for å hindre at utvikleren eller brukeren gjør feil.
- Eksempel: Lager funksjoner for å sette inn penger på kontoen istedenfor å endre på saldoen direkte.
- Eksempler: `std::vector` og `std::list` (og `std::cout` )
- APIer kan sees på som abstrakte datatyper – vi vet ikke hvordan koden hos verten fungerer, vi får kun et svar på vårt API-kall.

### std::map
- `std::map` er en datatype tilgjengelig i C++ standardbiblioteket
- Strukturert som et tre
- en `map` i C++ tilsvarer en `dict` i [[Kunnskap/Python\|Python]]
- Kan kun bruke nøkkelen til å hente ut en verdi
- Hvert element i mappet er et `std::pair` som har `.first` property som gir nøkkelen, og en `.second` som gir verdien

```cpp
std::map<int, std::string> students; // key, value, name
students[5] = "Lise Larsen"; // oppretter nøkkel dersom den ikke eksisterer
students[120] = "Fred Fredriksen";

for (auto &student : students) // auto iterator. Det på høyre side må være iterable
// & henter ut studenten som original (by-reference)
{
	std::cout << "Student" << student.first << ": " << student.second << std::endl;
}
```

## Templates
- En template-datatype kan være ulike datatyper i samme program

```cpp
template <class T>          // oppretter template
T sum(T num1, T num2) {     // bruker templaten i en funksjon
    return num1 + num2;
}

int main() {
	// avhengig av hvilken datatype vi kaller `sum` med nå, så forstår kompilatoren
	// hvilken datatype templaten skal benytte. IMPLISITT.
    int result = sum(2, 3); 
    double result2 = sum(2.3, 7.5);
}
```

## Operator overloading
Operator overloading er en funksjon som er knyttet til en spesifikk datatypen. Operator overloadfunksjonen forteller kompilatoren hvordan den skal tolke en tidligere udefinert operator for datatypene. For eksempel kan vi selv definere hvordan vi skal «legge sammen» to instanser av klassen `student`

 ```cpp
 struct Student {
     int id;
     std::string name;
 };
 
 Student operator+(const Student &s1, const Student &s2) {
     Student temp;
     temp.id = s1.id + s2.id;
     temp.name = s1.name + s2.name;
     return temp;
 }
 
 int main() {
     Student s1, s2;
     Student s3 = s1 + s2;
 }
 ```

## Forelesningsslides
<iframe src="https://docs.google.com/presentation/d/1PjQ0VvbDafFsukK-Kz-2SExbFV-lqe1OzcYcDUizjBE/edit?usp=sharing" width="100%" style="aspect-ratio:4/3;"></iframe>

## Video
![](https://www.youtube.com/live/SSTy_VEOH8A)
