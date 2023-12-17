# um-eecs467.github.io

University of Michigan EECS467 course website. Built with Jekyll ([documentation](https://jekyllrb.com/docs/)).

## Add pages
A new page can be added automatically by simply adding a `.html` file or `.md` file under the root directory. The following Front Matter should be added at the beginning of each page.

    ---
    layout: page
    title: <Title>
    ---

## Edit staff and projects
The information of staff and projects are stored under `/_data/`. User can edit staff and projects through the YAML files without taking care of pages.

Also, don't forget to upload the photo into `/assets/img/` if you are adding a staff.