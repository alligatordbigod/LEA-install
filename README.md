# Instalação LEA

# Instalando o R

<details open>
	<summary>Windows</summary>
Teste
</details>

<details>
	<summary>Ubuntu, debian e derivados (Linux, APT)</summary>
Teste 2
</details>

<details>
	<summary>Fedora RPM (yum, dnf)</summary>
Teste 3
</details>

<details open>
	<summary>Arch (pacman, yay)</summary>
  
Pré-requisitos do sistema:
 - AUR Helper (como o [yay](https://github.com/Jguer/yay))
 - GCC-Fortran (para compilar as bibliotecas do R)

Para instalar o GCC-Fortran, basta rodar no terminal:

```{bash}
sudo pacman -S gcc-fortran --noconfirm
```

Para instalar o RStudio (e o R), basta rodar no terminal:

```{bash}
yay -S --noconfirm rstudio-desktop-bin
```

Os seguintes passos da instalação serão executados já no console do RStudio.  

Pré-requisitos do R (RStudio):
- tidyverse (necessidade geral, apesar de não obrigatório para o modelo LEA)
- tinytex (para compilar o relatório e slides)
- devtools (para importar e compilar o modelo)

No linux, o `tidyverse` precisa de mais um pré-requisito (além do gcc-fortran) para ser compilado corretamente, para instalar esse pré-requisito rode no console do RStudio:

```{r}
install.packages("xml2")
```

Com o pré-requisito instalado, rode no console:

```{r}
install.packages("tidyverse")
```

> O tidyverse é um pacote grande, e como no linux o pacote deve ser compilado, talvez demore um pouco, espere o processo finalizar.

> Se houver erros, rode com o parâmetro `dependencies = TRUE`, ou seja:
> 
> ```{r}
> install.packages("tidyverse", dependencies = TRUE)
> ```

Para instalar o tinytex, rode os comandos (cada linha individualmente):

```{r}
install.packages("tinytex")
tinytex::install_tinytex()
```

É recomendado **reiniciar o RStudio** após instalar o tinytex, para ter certeza que foi instalado corretamente.
 
> Caso queira checar se a instalação do tinytex foi feita corretamente, rode no console:
> ```{r}
> tinytex::is_tinytex()
> ```
> Caso a instalação tenha sido realizada corretamente, o retorno do comando deve ser `TRUE`, caso contrário, reinstale o tinytex

> Caso o tinytex não tenha sido instalado corretamente (o retorno de `tinytex::is_tinytex()` é `FALSE`), tente reinstalar o pacote pelo gerenciador do R (`install.packages("tinytex")`) e pelo gerenciador do tinytex, da forma:
> ```{r}
> tinytex::install_tinytex(force = TRUE)
> ```

Para instalar o devtools, rode o comando:

```{r}
install.packages("devtools")
```

Com isto, todos os pré-requisitos para baixar o modelo LEA estão prontos, e seguiremos para a instalação do modelo.  
Para instalar o modelo LEA, rode no console (cada linha individualmente):

```{r}
library(devtools)
install_github("mnunes/modeloLEA")
```

Com isto o modelo LEA está instalado e os arquivos já podem ser criados.  

**Porém, o processo de instalação ainda não acabou**. Para compilar o relatório e os slides do modelo LEA ainda são necessários alguns outros pré-requisitos não necessariamente explicitados, estes são:

- babel-portuges (pacote de linguagem do tinytex, _é realmente digitado portuges_, único requisito para o relatório)
- ggfortify (pacote do r, requisito para slides)
- pdfcrop (pacote do tinytex, requisito para slides)
- (ghostscript)[https://ghostscript.com/releases/gsdnld.html] (pacote do sistema, requisito para slides)

</details>

<details>
	<summary>flatpak</summary>
Teste 5
</details>
