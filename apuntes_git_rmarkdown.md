Apuntes Git y RMarkdown
================
Patricio Said

25 de mayo de 2019

Ver la versión web (https://patosaid.github.io/apuntes_git_rmarkdown/)

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
-   Diagramas del flujo de trabajo en GitHub (<https://guides.github.com/introduction/flow/>)

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

> Para subir este documento a github: en yalm puse `output: github_document` para que cree un archivo (.md) aparte del (.Rmd). en la consola de GIT BACH me dirigí a la carpeta local que contiene este archivo, luego revisé `git status` , añadí los archivos con `git add .` (el punto es para subir todos los documentos q cambiaron, el .Rmd y .md, y los subí para comparar las salidas), luego un commit `git commit -m "formato github(por ejemplo)"` y finalmente un push, `git push`. Ahora se puede ver el documento en la pagina de GitHub con los render correspondientes de las sintaxis Markdown (el .md).

**Ahora, cómo publicar un documento tipo blog hosteando la página con GitHub Pages**

**Fuente:** (<https://resources.github.com/whitepapers/github-and-rstudio/>)

(En RStudio ir a Tools&gt; Global options&gt; Git y en el PATH debe estar git.exe C:/Program Files/Git/bin/git.exe )

1.  Crear nuevo proyecto: File &gt; New project &gt; Version control &gt; Git
2.  Pegar la URL del repositorio creado en GitHub , en mi caso: <https://github.com/patosaid/apuntes_git_rmarkdown.git>
3.  Clic en crear. (esto hace que se clone el repo en la carpeta q elegí... quedó la cagá, tengo un repo clonado dentro de un repo...)
4.  Crear un documento (este mismo)

**Commit and push the changes to GitHub**

After you have created the R Markdown document and finished making your changes, it is time to commit them.

1.  In RStudio click the `Git` tab in the upper right pane.(*bien, ahora me aparece , puse guardar los cambios para que aparezca para hacer commit* )
2.  Click `Commit`. (*ok*)
3.  In the Review changes view, check the staged box for all files. (*ok*)
4.  Add a commit message, for example Add initial speed and distance report. (*ok*)
5.  Click `Commit`. (*ok*)
6.  Click the `Pull` button to fetch any remote changes. (*ok*)
7.  Click the `Push` button to push your changes to the remote repository. (*ok*)
8.  On GitHub, navigate to the Code tab of the repository to see the changes. (*ok*)

Olvidé el archivo .md, repito los pasos anteriores para añdirlo.

*Create local branches with Git*

Let's make a couple of more changes in your project using the steps of GitHub Flow. As RStudio currently does not support local branches very well, we will use Git from the command-line in RStudio.

1.  In RStudio click the `Terminal` tab in the lower left pane. The `Terminal` tab is next to the Console tab.
2.  Create a new branch. Replace <BRANCH-NAME> with a descriptive name, yo le puse "new-branch": `git branch new-branch`
3.  Check your repository's status: `git status`
4.  Check out to your new branch: `git checkout new-branch`
5.  Verify that you are now checked out to your new branch: `git status`

*Make local changes with Git*

Let's generate the HTML output in a separate directory called docs. To do this we add a function in the heading of the R Markdown document to "knit" the output in the desired output directory.

1.  In RStudio open el archivo .Rmd (en mi caso es este mismo documento `apuntes_git_rmarkdown.Rmd`) and add the following lines in the heading under the title field:

``` r
knit: (function(input_file, encoding) {
  out_dir <- 'docs';
  rmarkdown::render(input_file,
 encoding=encoding,
 output_file=file.path(dirname(input_file), out_dir, 'index.html'))})
```

(*En el yalm tuve q sacar `output: github_document`*)

(*También tuve que crear una carpeta llamada docs para que guardara el archivo index.htlm ya que me salia error*)

1.  Click `File`, Save to save the changes.

**Commit local changes with Git**

After you have created the HTML output, it is time to commit the changes.

1.  Determine your file's status. Remember that `git status` allows us to see the status of the files on our branch at any given time. Your file is listed under the heading `Untracked files`: `git status`
2.  Add your file to the staging area so it's prepared to become part of the next commit: `git add .`
3.  See your file's current status. Your file is now listed under the heading `Changes to be committed`. This tells us that the file is in the staging area. It also indicates this is a new file: `git status`
4.  Commit your file. Replace `<COMMIT-MESSAGE>` with a log message describing the changes, for example `Knit output to a docs folder`. A commit tells Git to collect all of the files in the staging area and store them to version control as a single unit of work: `git commit -m "<COMMIT-MESSAGE>"`
5.  See the history of commits: `git log --online` (*me salió error*)
6.  See the changes between the master branch and the current branch (HEAD): `git diff --stat --summary master..<BRANCH-NAME>`

**Open a pull request on GitHub**

Now that you have made some local commits, it is time to send your changes to the remote copy of your repository on GitHub and create a Pull Request.

1.  Push the changes to the remote repository: `git push -u origin <BRANCH-NAME>`
2.  Create a [Pull Request](https://help.github.com/en/articles/creating-a-pull-request) on GitHub. Fill out the body of the Pull Request with information about the changes you're introducing.
3.  Fill out the body of the Pull Request with information about the changes you're introducing.

**Merge your pull request on GitHub**

Since this is your repository, you probably don't have anyone to collaborate with (yet). Go ahead and merge your Pull Request now.

1.  On GitHub, navigate to the `Pull Request` that you just opened.
2.  Scroll down and click the big green `Merge Pull` Request button.
3.  Click `Confirm Merge`.
4.  Delete the branch <BRANCH-NAME>.

CREAR LA PAGINA! porfin
=======================

This tutorial is going to use GitHub Pages to publish the HTML output. To initialize GitHub Pages we need to perform a few more steps:

1.  In your repository, click the `Settings` tab.
2.  Scroll down to the `GitHub Pages` section.
3.  Under `Source`, select `master branch /docs folder`.
4.  Click `Save` to save the changes.
5.  Click the generated GitHub Pages URL to view the rendered R Markdown document.

**Note:** GitHub Pages sites are always public when hosted on GitHub.com. If you want to share a site with a select number of people you can use Jekyll Auth. On GitHub Enterprise users need to authenticate to access GitHub Pages sites when private mode is enabled.

**Update local repository**

After you merge your Pull Request, you will need to update your local copy of the repository.

1.  In the RStudio Terminal pane, type: `git checkout master`
2.  Type: `git pull`
3.  Delete the local branch: `git branch -D <BRANCH-NAME>`
4.  See the history of your commits in a graph: `git log --oneline --graph --all`

You can also view the history of your commits in RStudio. Click Commit in the Git pane to open the Review Changes panel and then click History.
