# Clean Code – Praktische Leitfaden

## Was ist Clean Code?

Clean Code ist der Ansatz, Code zu schreiben, der nicht nur funktioniert, sondern auch leicht zu verstehen, zu warten und zu erweitern ist. Es geht darum, dass andere Entwickler (oder du selbst nach Monaten) deinen Code schnell erfassen können, ohne lange rätseln zu müssen.

### Warum ist Clean Code wichtig?

- **Wartbarkeit**: Code wird häufiger gelesen als geschrieben. Sauberer Code spart Zeit beim Verstehen.
- **Fehlerreduzierung**: Klarer, strukturierter Code führt zu weniger Bugs.
- **Zusammenarbeit**: Im Team brauchst du Code, den andere schnell verstehen können.
- **Professionalism**: In der Berufswelt ist Clean Code ein Standard – nicht optional.
- **Eigener Anspruch**: Guter Code zu schreiben ist Handwerk, nicht einfach nur funktionieren lassen.

---

## Beispiel 1: Aussagekräftige Variablennamen

### ❌ Nicht gut – Code ohne Aussagekraft
```java
public class User {
    String u;
    int a;
    String bd;
    boolean ac;

    public User(String u, int a, String bd, boolean ac) {
        this.u = u;
        this.a = a;
        this.bd = bd;
        this.ac = ac;
    }

    public String proc() {
        if (ac && a > 18) {
            return u + " ist " + a + " Jahre alt.";
        }
        return "";
    }
}
```

**Probleme:**
- `u`, `a`, `bd`, `ac` – Diese Variablennamen sagen nichts aus. Was bedeuten diese Buchstaben?
- Wer liest diesen Code in 2 Wochen noch, kann sich nicht mehr vorstellen, was gemeint ist.
- Fehler entstehen leicht, weil unklar ist, was jede Variable macht.
- Im Team: Andere müssen lange fragen, was das bedeutet.
- Sogar die Methoden-Namen sind undefiniert.

---

### ✅ Gut – Clean Code mit aussagekräftigen Namen
```java
public class User {
    private String userName;
    private int userAge;
    private String userBirthDate;
    private boolean isUserActive;

    public User(String userName, int userAge, String userBirthDate, boolean isUserActive) {
        this.userName = userName;
        this.userAge = userAge;
        this.userBirthDate = userBirthDate;
        this.isUserActive = isUserActive;
    }

    public String printUserProfile() {
        if (isUserActive && userAge > 18) {
            return userName + " ist " + userAge + " Jahre alt.";
        }
        return "Der Benutzer ist nicht aktiv oder nicht volljährig.";
    }

    public String getUserName() {
        return userName;
    }

    public int getUserAge() {
        return userAge;
    }
}
```

**Vorteile:**
- `userName`, `userAge`, `userBirthDate`, `isUserActive` – Sofort klar, was gemeint ist.
- Der Code ist selbsterklärend. Keine Geheimnisse, keine Verwirrung.
- Fehler werden schneller erkannt, weil die Absicht deutlich ist.
- Beim Code-Review verstehen Kollegen sofort, was läuft.
- Du selbst fragst dich nach 3 Monaten nicht mehr: „Was war das nochmal?"
- Getter-Namen sind aussagekräftig und folgen Java-Konventionen.

**Warum ist das wichtig?**

Das erste Beispiel sieht vielleicht beim Schreiben wie eine Zeiteinsparung aus („Ich spare 2 Sekunden!"), aber das ist Selbstbetrug. Der Code wird tausendfach gelesen. Eine aussagekräftige Variable kostet beim Schreiben vielleicht 3 Sekunden mehr, spart aber in der Zukunft Stunden ein – bei dir und bei deinem Team. Unklar geschriebener Code wird zur technischen Schuld, die dein Team ausbaden muss. In großen Java-Projekten mit vielen Klassen wird dieser Effekt noch dramatischer.

---

## Zusammenfassung (aktuell)

| Aspekt | Bedeutung |
|--------|-----------|
| **Variablennamen** | Sollen klar ausdrücken, was sie enthalten |
| **Selbserklärend** | Code sollte seine Absicht ohne lange Kommentare zeigen |
| **Wartbarkeit** | Klarer Code ist günstiger in der langfristigen Pflege |
| **Java-Konventionen** | Camel Case, aussagekräftige Getter/Setter |

---

## Was kommt noch?

Diese Datei wird laufend erweitert mit weiteren Clean Code Prinzipien:
- Methoden: Kleine, fokussierte Methoden (Single Responsibility)
- Kommentare: Wann sinnvoll, wann nicht
- DRY-Prinzip: Keine Wiederholungen
- Fehlerbehandlung
- Klassen-Design
- und vieles mehr...

**Status**: Täglich erweitert 📚

---

*Dieses Projekt zeigt praktische Clean Code Konzepte mit echten Beispielen.*
