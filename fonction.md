# 📘 Résumé des verbes COBOL les plus importants

Ce document résume les **verbes (instructions)** COBOL les plus utilisés, leur **utilité** et **comment les utiliser**, avec des exemples simples.

> Quand on parle de « fonctions » en COBOL, on parle en réalité de **verbes** (statements).

---

## 🔹 MOVE

### Utilité

Copier une valeur dans une autre variable.

### Syntaxe

```cobol
MOVE source TO destination
```

### Exemple

```cobol
MOVE 10 TO WS-NUMBER
MOVE WS-NAME TO WS-NAME-COPY
```

---

## 🔹 COMPUTE

### Utilité

Effectuer un calcul arithmétique.

### Syntaxe

```cobol
COMPUTE resultat = expression
```

### Exemple

```cobol
COMPUTE WS-TOTAL = WS-PRICE * WS-QUANTITY
```

Opérateurs possibles : `+  -  *  /  **`

---

## 🔹 ADD / SUBTRACT / MULTIPLY / DIVIDE

### Utilité

Effectuer des calculs simples sans `COMPUTE`.

### Exemples

```cobol
ADD 5 TO WS-NUMBER
SUBTRACT 2 FROM WS-NUMBER
MULTIPLY WS-A BY WS-B
DIVIDE WS-TOTAL BY WS-COUNT GIVING WS-AVERAGE
```

---

## 🔹 DISPLAY

### Utilité

Afficher un message ou une variable à l'écran.

### Syntaxe

```cobol
DISPLAY expression
```

### Exemple

```cobol
DISPLAY "Bonjour"
DISPLAY WS-NAME
```

---

## 🔹 ACCEPT

### Utilité

Lire une entrée utilisateur.

### Syntaxe

```cobol
ACCEPT variable
```

### Exemple

```cobol
ACCEPT WS-NAME
```

---

## 🔹 IF / ELSE / END-IF

### Utilité

Exécuter du code selon une condition.

### Syntaxe

```cobol
IF condition
   instructions
ELSE
   instructions
END-IF
```

### Exemple

```cobol
IF WS-AGE >= 18
   DISPLAY "Majeur"
ELSE
   DISPLAY "Mineur"
END-IF
```

---

## 🔹 PERFORM

### Utilité

Exécuter un paragraphe ou une boucle.

### Exécuter un paragraphe

```cobol
PERFORM CALCUL-TOTAL
```

### Boucle simple

```cobol
PERFORM VARYING I FROM 1 BY 1 UNTIL I > 10
   DISPLAY I
END-PERFORM
```

---

## 🔹 EVALUATE (équivalent du SWITCH)

### Utilité

Gérer plusieurs cas selon une valeur.

### Syntaxe

```cobol
EVALUATE variable
   WHEN valeur1
      instructions
   WHEN valeur2
      instructions
   WHEN OTHER
      instructions
END-EVALUATE
```

### Exemple

```cobol
EVALUATE WS-CHOICE
   WHEN 1
      DISPLAY "Option 1"
   WHEN 2
      DISPLAY "Option 2"
   WHEN OTHER
      DISPLAY "Invalide"
END-EVALUATE
```

---

## 🔹 OPEN / READ / WRITE / CLOSE (FICHIERS)

### OPEN

```cobol
OPEN INPUT FILE-IN
OPEN OUTPUT FILE-OUT
```

### READ

```cobol
READ FILE-IN
   AT END
      MOVE 'Y' TO EOF-FLAG
END-READ
```

### WRITE

```cobol
WRITE RECORD-OUT
```

### CLOSE

```cobol
CLOSE FILE-IN FILE-OUT
```

---

## 🔹 INITIALIZE

### Utilité

Réinitialiser une ou plusieurs variables.

### Exemple

```cobol
INITIALIZE WS-TOTAL WS-COUNT
```

---

## 🔹 SET

### Utilité

Modifier des index, flags ou variables conditionnelles.

### Exemple

```cobol
SET EOF-TRUE TO TRUE
SET I UP BY 1
```

---

## 🔹 STOP RUN

### Utilité

Terminer le programme.

```cobol
STOP RUN
```

---

## 🔹 CALL

### Utilité

Appeler un autre programme COBOL.

### Exemple

```cobol
CALL 'PGM2' USING WS-DATA
```

---

## 🔹 STRING / UNSTRING

### STRING (concaténer)

```cobol
STRING WS-NOM ' ' WS-PRENOM
   INTO WS-NOM-COMPLET
END-STRING
```

### UNSTRING (découper)

```cobol
UNSTRING WS-DATA
   DELIMITED BY ','
   INTO WS-A WS-B
END-UNSTRING
```

---

## 🔹 INSPECT

### Utilité

Compter, remplacer ou analyser une chaîne.

### Exemple

```cobol
INSPECT WS-TEXT TALLYING WS-COUNT FOR ALL 'A'
```

---

## 📌 Conclusion

Ces verbes représentent **90 % du COBOL utilisé en entreprise**. Les maîtriser permet de :

* Lire du code legacy
* Écrire des programmes batch
* Travailler avec des fichiers et des données métier

👉 Si tu veux, je peux aussi te faire :

* un **mémo ultra court (cheat sheet)**
* des **exercices corrigés**
* un **exemple de programme COBOL complet commenté**
