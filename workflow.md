###Branch Organization

- `gh-pages` should always contain the latest release version of public website
- `master` is the main development branch. Alternate development branches can also be used, after which their content should be merged into `master`.

###Workflow

__'master' as development branch__

    # Make changes to file(s) in master branch
    git commit -am "<commit message>"
    git push
    git checkout gh-pages
    git merge master
    git push
    git checkout master

__Different development branch__

    # Make changes to file(s) in <devbranch>
    git commit -am "<commit messsage>"
    git checkout master
    git merge <devbranch>
    git push
    git checkout gh-pages
    git merge master
    git push
    git checkout master
    git branch -d <devbranch>

###File Organization

    Electromagnetics-Visualizations (github repository)
        master branch
            index.html
            README.md
            static/
                common js and css files such as header/nav/footer for each page
            Visualization 1/
                <filename.html>
                static/
                images/
            Visualization 2/
                <filename.html>
                static/
                images/
        gh-pages branch  # same organization & same files as master
    Independent project repository  # Use rawgit to link to
        master branch
            <filename.html>
            README.md
            static/
                js and css files
                images/
