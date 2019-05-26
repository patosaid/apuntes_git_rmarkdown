Apuntes Git y RMarkdown
================
Patricio Said
25 de mayo de 2019

------------------------------------------------------------------------

<!-- así se ponen comentarios en rmarkdown-->
### Un poco de documentación:

-   [Cheat sheet de Rmarkdown](https://www.rstudio.com/wp-content/uploads/2016/03/rmarkdown-cheatsheet-2.0.pdf)
-   [Sintaxis para documentos en GitHub (markdown)](https://help.github.com/en/articles/basic-writing-and-formatting-syntax)
-   Página de Git, manuales, libros, documentos en español: [got-scm.com](https://git-scm.com/book/es/v2)
-   Un blog de apuntes corto de [Git/GitHub](https://libreim.github.io/blog/2014/02/23/manualgit/)
-   Un repositorio de apuntes: [aprende Git "curso"](https://github.com/JJ/aprende-git)
-   Otro repositorio de apuntes: [aprende Git](https://github.com/DGIIMUnderground/DGIIM1)
-   Aprender Git y GitHut con [Codecademy](https://www.codecademy.com/courses/learn-git/)
-   Libro [blogdown: Creating Websites with R Markdown](https://bookdown.org/yihui/blogdown/) y el [Repo. en GitHub](https://github.com/rstudio/blogdown)
-   Libro [R Markdown: The Definitive Guide](https://bookdown.org/yihui/rmarkdown/) (**VER**)
-   Instrucciones de GitHub / RStudio (<https://resources.github.com/whitepapers/github-and-rstudio/>) (**VER**)
-   RMarkdown formato de documentos GitHub (<https://rmarkdown.rstudio.com/github_document_format.html>) (**VER**)

------------------------------------------------------------------------

**Nota:**

> El **objetivo** de este documento se enfoca en la creación y publicación de un post formato blog. Se mostrará paso a paso, desde la escritura en Rmarkdown hasta publicación en GitHub.

Elementos de RMarkdown
----------------------

RMarkdown y GitHub utilizan la sintaxis de Markdown para reproducir facilmente formatos de escrituras (html en este caso). Para escribir un documento bien estructurado es fundamental conocer los elementos básicos para crear un texto: títulos, subtítulos, listas, letras en cursivas o en negritas, citas, etc. Por ejemplo en RMarkdown, para diferenciar un parafo de otro se deben separar por una lina de código vacía.

### Sintaxis básicas

A continuación se presenta algunas de las principales sintaxis y en la linea siguiente la salida o (render) correspondiente:

`# Ejemplo de título grande`

Ejemplo de título grande
========================

`### Ejemplo de un sub título`

### Ejemplo de un sub título

`*cursiva*` y `*negrita*`

*cursiva* y **negrita**

<code>\`formato código\`</code>

`formato código`

`superindice^2^ y subindice~2~`

superindice<sup>2</sup> y subindice<sub>2</sub>

`~~tachado~~`

~~tachado~~

\* \_ \\

`Poner signos: \* \_ \\`

Poner signos: \* \_ \\

`--`

--

`---`

------------------------------------------------------------------------

`Ecuación en linea $A=\pi*r^2$`

Ecuación en linea *A* = *π* \* *r*<sup>2</sup>

`$$A=\pi*r^2$$`

*A* = *π* \* *r*<sup>2</sup>

`Saltar a [Ejemplo de título grande]`

Saltar a [Ejemplo de título grande](#ejemplo-de-título-grande)

`> Cita`

> Cita

`<https://psaid.shinyapps.io/AInsigne/>`

<https://psaid.shinyapps.io/AInsigne/>

`[Link a AInsigne](https://psaid.shinyapps.io/AInsigne/)`

[Link a AInsigne](https://psaid.shinyapps.io/AInsigne/)

`* item de lista` `* otro item` `+ sub item` `- sub sub item`

-   item de lista
-   otro item
    -   sub item
        -   sub sub item

`* otro item`

-   otro item

`***`

------------------------------------------------------------------------

-   Las sintaxis presentadas son algunas que se pueden utilizar en Rmarkdown, pero hay otras que funcionan en [GitHub](https://help.github.com/en/articles/basic-writing-and-formatting-syntax):

-   \[x\] Finish my changes
-   \[ \] Push my commits to GitHub
-   \[ \] Open a pull request

### Comandos básicos de git en consola

-   `git init` creates a new Git repository.
-   `git status` inspects the contents of the working directory and staging area.
-   `git add` adds files from the working directory to the staging area.
-   `git diff` shows the difference between the working directory and the staging area.
-   `git commit` permanently stores file changes from the staging area in the repository.
-   `git log` shows a list of all previous commits.

<https://github.com/DGIIMUnderground/DGIIM1/blob/master/guias/github.md> <https://github.com/JJ/aprende-git/blob/master/texto/uso_basico.md>

### git reset review

To better understand git reset commit\_SHA, notice the diagram on the right. Each circle represents a commit.

**Before reset:**

-   `HEAD` is at the most recent commit

**After resetting:**

-   `HEAD` goes to a previously made commit of your choice
-   The gray commits are no longer part of your project
-   You have in essence rewound the project's history

-   `git checkout HEAD filname`: Discards changes in the working directory.
-   `git reset HEAD filname`: Unstages file changes in the staging area.
-   `git reset commit_SHA`: Resets to a previous commit in your commit history.

**git branch:**

Git branching allows users to experiment with different versions of a project by checking out separate branches to work on. The following commands are useful in the Git branch workflow.

-   `git branch`: Lists all a Git project's branches.
-   `git branch branch_name`: Creates a new branch.
-   `git checkout branch_name`: Used to switch from one branch to another.
-   `git merge branch_name`: Used to join file changes from one branch to another.
-   `git branch -d branch_name`: Deletes the branch specified.

Iniciando con Git y GitHub
--------------------------

#### BitHub

Para usar **GitHub** se debe crear una cuenta en <https://github.com/>.

#### Git

Para instalar **Git** visitar [git-scm.com/downloads](https://git-scm.com/downloads).

Luego de instalar Git se debe configurar el nombre de usuario y email.

**Configurar Git**

1.  Abrir "Git Bash"
2.  Configurar nombre de usuario:

`git config --global user.name "Nombre que quieras mostrar"`

1.  Configurar email del usuario:

`git config --global user.email "correo@email.com"`

Ver <https://help.github.com/en/articles/set-up-git> para mas información.

Para crear un repositorio en Git se suele usar las linas de comandos, algunas son:

**Lineas de comandos:**

-   `ls`
-   `pwd`
-   `cd`
-   `cd ..`
-   `mkdir`: crea un directorio
-   `touch`: crea un archivo

**Ahora usémoslas para crear un repositorio:**

1.  `mkdir git_practice` to make a new directory to practice.
2.  `cd git_practice` to make the new directory your working directory.
3.  `git init` to turn the current, empty directory into a fresh Git repository.
4.  `echo "Hello Git and GitHub" >> README.txt` to create a new README file (more on this later) with some sample text.
5.  `git add README.txt` to add the new file to the Git staging area.
6.  `git commit -m "First commit"` to make your first commit with the new README file.

A remote is a Git repository that lives outside your Git project folder. Remotes can live on the web, on a shared network or even in a separate folder on your local computer. The Git Collaborative Workflow are steps that enable smooth project development when multiple collaborators are working on the same Git project. We also learned the following commands

-   `git clone`: Creates a local copy of a remote.
-   `git remote -v`: Lists a Git project's remotes.
-   `git fetch`: Fetches work from the remote into the local copy.
-   `git merge origin/master`: Merges origin/master into your local branch.
-   `git push origin <branch_name>`: Pushes a local branch to the origin remote.

Git projects are usually managed on Github, a website that hosts Git projects for millions of users. With Github you can access your projects from anywhere in the world by using the basic workflow you learned here.

**Ahora un repositorio remoto con GitHub:**

Fuente:
