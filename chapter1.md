---
title: 'Andmete import'
description: 'Testime andmete importimise erinevaid võimalusi.'
---

## Andmete import

```yaml
type: NormalExercise
key: 56fa6fa7e3
lang: r
xp: 100
skills: 1
```

Andmete impordiks tekstifailist saab kasutada käsku `read.table()`. 

Funktsiooni `read.table()` argumentide abil saab paika panna, mis on imporditavas failis veergude eraldaja, mis sümbolit kasutatakse kümnendkoha määramisel, kas veergudel on olemas nimed jne.

`@instructions`
- **Ülesanne 1** Kasutades käsku `read.table()` impordi R-i fail nimega *katsed.txt* aadressilt  *http://kodu.ut.ee/~annes/R/katsed.txt*, omista andmestik muutujale `andmed1`. Prindi andmestik ekraanile.
- **Ülesanne 2** Vaata andmestiku struktuuri käsuga `str()`.

`@hint`
- Ava fail brauseri aknas ja vaata, mis on veergude eraldaja. 
- Imporditud andmetabelis peab olema 6 vaatlust ja 3 tunnust.

`@pre_exercise_code`
```{r}
# Load datasets and packages here.
```

`@sample_code`
```{r}
# Ülesanne 1: Impordi andmed, moodustades objekti andmed1. Prindi saadud objekt ekraanile
andmed1 <- read.table(_________________________________)
__________


# Ülesanne 2: Vaata andmestiku struktuuri


 

```

`@solution`
```{r}
# Ülesanne 1: Impordi andmed, moodustades objekti andmed1. Prindi saadud objekt ekraanile
andmed1 <- read.table("http://kodu.ut.ee/~annes/R/katsed.txt", header = T, sep = "\t")
andmed1


# Ülesanne 2: Vaata andmestiku struktuuri
str(andmed1)



```

`@sct`
```{r}

success_msg("Tubli! Pane tähele, et impordil tekkisid väga pikad tunnusenimed. Seega nõuavad imporditavad failid vahel ka eeltööd. Siin oleks eelnevalt tulnud tekstifailis tunnusenimesid kohendada, need peaks olema sisukad, kuid võimalusel mitte väga pikad. Veerupäistes olevad tühikud ja erisümbolid teisendatakse punktideks. Teine võimalus oleks argumendi `col.names` abil tunnustele uued nimed ette anda.")
```
