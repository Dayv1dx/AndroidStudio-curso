# Tipos de dados

- **Númerico**

    - Inteiro - _TynyInt, SmallInt, Int, MediumInt, BigInt_
    - Real - _Decimal, Float, Double, Real_
    - Lógico - _Bit, Boolean_

<br>

- **Data/Tempo** - _Date, DateTime, Timestand, Time, Year_

<br>

- **Textos**

    - Caractere - _Char, VarChar_
    - Texto - _TynyText, Text, MediumText, LongText_
    - Binário - _TynyBlob, Blob, MediumBlob, LongBlob_
    - Coleção - _Bit, Boolean_

<br>

## Principais tipos e seu armazenamento

É recomendado utilizar os tipos de acordo com o que será guardado, evitando, assim, uso demasiado de memória.

Tipo de número | Máx. de caracteres
---------------|-------------------
_TynyInt_ | -128 até 127
_SmallInt_ | -32.768 até 32.767
_Int_ | -8.388.608 até 8.388.607
_MediumInt_ | -2.147.483.648 até 2.147.483.647
_BigInt_ | -2^63 até 2^63

<br>

- CASAS DECIMAIS

(M é o número máximo de digitos e D a quantidade de casas decimais)

decimal(8,2) = 123456.78

Tipo de número | Máx. de caracteres
---------------|-------------------
_Float_ (M,D) | 8 casas decimais
_Double_ (M,D) | 16 casas decimais
_Decimal_ (M,D) | M até 65 e D até 30

<br>

Tipo de texto | Máx. de caracteres
---------------|-------------------
_TynyText_ | 255
_Text_  | 65.535
_MediumText_  | 16.777.215
_LongText_ | 4.294.967.295

<br>

Tipo de data | Formato
---------------|-------------------
_Date_ | AAAA-MM-DD
_DateTime_ | AAAA-MM-DD HH:MM:SS
_Year_  | AAAA
_Time_ | HH:MM:SS