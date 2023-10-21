# IT-Security
- [IT-Security](#it-security)
- [Einführung](#einführung)
  - [Safety](#safety)
  - [Security](#security)
  - [Cybercrime](#cybercrime)
- [Kryptologie](#kryptologie)
  - [Kryptographie](#kryptographie)
    - [symmetrische Kryptographie](#symmetrische-kryptographie)


# Einführung
## Safety
...

## Security  
Sicherheit vor (gezielten) Störungen von außen. 

...

- Authentizität
- Integrität
- nicht-Abstreitbarkeit
- Verbindlichkeit
- Verfügbarkeit
- Privatsphäre
- Vertraulichkeit


**Authentifizierung** <br>
Nachweis der Identität (Shared Secret, Biometrie, ...). 

**Verfügbarkeit** <br>
Vorhergesagte Nutzung durch vorhergesehene Nutzer ist möglich. 

**Privatsphäre** <br>
Grundrecht auf informationelle Selbstbestimmung (DSGVO), technisch hilft Anonymisierung.


## Cybercrime
...

# Kryptologie
Ist die Wissenschaft von der Verschlüsselung und Entschlüsselung von Informationen.

```mermaid
graph LR
    A[Kryptologie] --> B["Steganographie <br> (verstecken)"]
    A --> C[Kryptographie <br> verschlüsseln]
    A --> D[Kryptanalyse <br> entschlüsseln]
```

**Stenanographie** <br>
Technische Stenanographie ist zum Beispiel die Manipulation von Bild-, Audio- und Videodateien sowie Verstecken weiterer Dateien. 

## Kryptographie
Verschlüsselung von Informationen.

### symmetrische Kryptographie
Zum Beispiel Caesa oder ROT13 - z.B.Verschiebung des Alphabets um einen bestimmten Wert. 
Kryptanalyse mit Mono-, Bi oder Trigrammen sowie Brute-Force möglich.

```python
# Verschiebung um 3
ABCDEFGHIJKLMNOPQRSTUVWXYZ
XYZABCDEFGHIJKLMNOPQRSTUVW
# mit Caesar
Gdv lvw hlq Ehlvslho.
Das ist ein Beispiel.
```

...RC4 (S.94)

...Electronic Code Book Mode (S.98) 

...Cipher Block Chaining Mode (S.100)

...Cipher Feedback Mode (S.102)

**Data Encryption Standard** <br>
DES (USA, 1977) ist ein symmetrisches Blockchiffre mit 64 Bit Blockgröße (davon 56 Bit Schlüssel und 8 Bit Parität).

<details><summary>graphische Darstellung</summary>

```mermaid
graph TB
    A("64bit \n Klartext") --> B["Eingangs- \n Permutation"]
    B --> C["L-Block \n 32bit"]
    B --> D["R-Block \n 32bit"]
    C --> I((XOR))
    D --> E["Expansion \n 48bit"]
    E --> F(("XOR"))
    F --> G["S1 \n S2 \n ... \n Sn"]
    G --> H["Permutation \n 32bit"]
    I --> J["Ausgangs- \n Permutation \n 64bit"]
    J --> K("64bit \n Ciphertext")

    H --> I
    I --> D
    C --> J

    Q("Schlüssel \n 64bit") --> R["Schlüssel- \n Permutation"]
    R --> S["C-Block \n 28bit"]
    R --> T["D-Block \n 28bit"]
    S --> U["Schlüssel- \n auswahl \n 48bit"]

    U --> F
    T --> U
```

Siehe [Foliensatz](McBaumwolle/thi-notes/semester_7/security/skript/it_sicherheit_KI_krypto.pdf) S.82!

</details> <br>

**3DES** <br>
3DES ist eine Erweiterung von DES. 

**International Data Encryption Algorithm** <br>
IDEA ist eine symmetrische Blockchiffre mit 128bit-Schlüssel und 64bit-Blöcken, jeweils 8 Runden. 

**Advanced Encryption Standard** <br>
AES wurde 2000 "in Dienst gestellt" und ist eine symmetrische Blockchiffre mit 128bit-Blockgröße verschiedenen Schlüssellängen (128, 160, 192, 224, 256bit).

[Animation](https://www.cryptool.org/de/cto/aes-animation) & [Step-by-Step](https://www.cryptool.org/de/cto/aes-step-by-step)

**sicherer Schlüsselaustausch** <br>
Diffie-Hellman 

