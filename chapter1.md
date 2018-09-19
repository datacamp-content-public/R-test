---
title: 'Template Chapter 1'
description: 'This is a template chapter.'
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
# 1
test_function(name = "read.table",
              args = c("header", "sep"),
              index = 1,
             eq_condition = "equivalent",
             not_called_msg = "Esimeses ülesandes pead kasutama funktsiooni `read.table`",
             args_not_specified_msg = paste("Määra `read.table` käsus argumendi", c("`header`", "`sep`" ), "väärtus."),
             incorrect_msg = paste("Oled funktsioonis `read.table` andnud vale väärtuse argumendile",  c("`header`", "`sep`"))) 
 




test_data_frame("andmed1",  
                columns = c("siin.veerus..on.lause",  "uuritavate.identifikaator..see.on.nagu.nimi", "esimesel.katsel.saadud.tulemus..katse.toimus.hommikul.kell.8.30"),
                eq_condition = "equivalent",
                undefined_msg = "Andmestik `andmed1` on defineerimata.",
                undefined_cols_msg = "Kontrolli, mis tunnused on andmestikus `andmed1`.",
                incorrect_msg = "Objekti `andmed1` väärtus ei ole korrektne. Proovi uuesti.") 
 

 
test_output_contains(expr = "andmed1",
                     times = 1,
                     incorrect_msg = "Andmestik on ekraanile printimata")


success_msg("Tubli! Pane tähele, et impordil tekkisid väga pikad tunnusenimed. Seega nõuavad imporditavad failid vahel ka eeltööd. Siin oleks eelnevalt tulnud tekstifailis tunnusenimesid kohendada, need peaks olema sisukad, kuid võimalusel mitte väga pikad. Veerupäistes olevad tühikud ja erisümbolid teisendatakse punktideks. Teine võimalus oleks argumendi `col.names` abil tunnustele uued nimed ette anda.")
```
