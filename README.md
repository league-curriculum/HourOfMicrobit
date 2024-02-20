<<<<<<< HEAD
# Hour of Microbit
=======
# LevelX

Template for vuepress-based lesson websites. 


NOTE! This is a template repo, you probably want to use "Use this template" and not clone it. 


## Using this Repo


### Install the lesson builder program and vuepress

Install the lesson plan program 

```bash 
python -mvenv .venv
source .venv/bin/activate
pip install git+https://github.com/league-infrastructure/lesson-builder.git#egg=lesson-builder
```

Install vuepress, if you haven't already.  [See these instructions for details](https://vuepress.vuejs.org/guide/getting-started.html). 
in this example, we will be using `yarn` rather than `npm` to install vuepress.


If you have installed yarn previously, you will still need to install in the docs dir

```bash
 (cd docs &&  yarn install )
 ```


### Install Lessons

You can copy lessons into the `lessons` directory, or create new a new one with 

```bash
jtl new plan lessons -F
```

This should result in a new ```lesson-plan.yaml``` file in the lessons directory



### Install Assignments. 

Now install some assigments in the assignments directory. You can clone them
from another repository, or create them with `jtl new assignment`. Here we will
create one called `new_assignment`. However, assignments are typically
organized into lessons, which are just sub-directories in the assignments. So, 
we will create a lesson directory first, but you don't really have to. 

```bash
cd assignments
mkdir lesson1
cd lesson1
jtl new assignment new_assignment
cd ../..
```

Or, you can also clone into assignments directory, for instance:

```bash 
cd assignments && git clone https://github.com/League-central/python-modules.git)
```


### Link assignments to the lesson plan

Now, edit ``lessons/lesson-plan.yaml`` to link to your new assignment. We will use
the `assignments` directory as the root for assignments, so your new assignment will 
be named relative to that directory, `lesson/new_assignment`.  Here is what the
lessons section in the default lesson-plan.yaml file looks like:

```yaml
lessons:
  lesson1:
    text: lesson1.md
    resources:
      - flag.png
    assignments:
    - python-modules/Levels/Level0/Module0/01_drawing/tina_the_turtle
    - python-modules/Levels/Level0/Module0/01_drawing/shapes_and_colors
```

The `python-modules` prefix is what you would use if you'd cloned `python-modules.git` into the
assignments directory.


If you created a new assignment, we will change that to:

```yaml
lessons:
  lesson1:
    text: lesson1.md
    resources:
      - flag.png
    assignments:
    - lesson1/new_assignment
```

### Build the  Website source

Now you can build your website. 

```bash 
$ jtl -vv build -l lessons -a assignments -d docs
INFO:lesson_builder.cli.jtl:Using url base 'LevelX'
INFO:lesson_builder.lesson:Writing lesson plan to docs/src/lessons
DEBUG:lesson_builder.lesson:Writing Lesson Introduction to Tina the Turtle to docs/src/lessons/introduction-to-tina-the-turtle
DEBUG:lesson_builder.lesson:        Copying flag.png to docs/src/lessons/introduction-to-tina-the-turtle
DEBUG:lesson_builder.lesson:        Writing Shapes and Colors
```


### Serve the website. 

```bash
jtl serve
```

If you get errors, it maybe because you need to install packages with yarn. Try: `(cd docs &&  yarn install )`

If it works, visit  http://localhost:8080/LevelX/ to see you site. 

>>>>>>> 98f23b8 (.)



## Lesson plan


1. Explore OOB experience
  * Instructore need to prepare all mb before hand. 
2. Beating Heart Program, demo emulator, get uopload working
3. Buttons to make happy/sad. 
  * Change to shape to make sad, button to make happy
4. Image scroll
  * buttons make number go up and down, display number
  * If statement to display image on some numbers
5. Rock Paper Scisors
  * Button selects random number
  * If statement to display image. 


