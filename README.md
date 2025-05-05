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

<details>
	<summary>Arch (pacman, yay)</summary>

- Pré-requisitos:
 - AUR Helper (como o (yay)[https://github.com/Jguer/yay])
 - GCC-Fortran (para compilar as bibliotecas do R)

Para instalar o GCC-Fortran, basta rodar no terminal:

```{bash}
sudo pacman -S gcc-fortran --noconfirm
```

Para instalar o RStudio (e o R), basta rodar no terminal:

```{bash}
yay -S --noconfirm rstudio-desktop-bin
```

Os seguintes passos da instalação serão executados já dentro do RStudio.
Abra o RStudio, e instale o `tidyverse`, que será necessário para utilizar o modelo LEA, seguindo os passos à seguir.
No linux, o `tidyverse` precisa de mais um pré-requisito (além do gcc-fortran) para ser compilado corretamente, rode no terminal do RStudio:

```{r}
install.packages("xml2")
```

Com o pré-requisito instalado, rode no terminal do RStudio:

```{r}
install.packages("tidyverse")
```

Se houver erros, rode com o parâmetro `dependencies = TRUE`, ou seja:

```{r}
install.packages("tidyverse", dependencies = TRUE)
```

Agora, para iniciar a instalação do modelo LEA, temos os pré-requisitos:

- tinytex

Para instalar o tinytex, rode os comandos (cada linha individualmente):

```{r}
install.packages("tinytex")
tinytex::install_tinytex()
```

</details>

<details>
	<summary>flatpak</summary>
Teste 5
</details>
