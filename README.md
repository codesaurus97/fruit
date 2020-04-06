# Fruit

The readme is under development...

## Roadmap

- yaml syntax checking for step types
- step type: `fruit` to ripen a fruit inside a ripening
- better documentation
- implement unit tests


## The fruits

The fruits (`fruit.yaml`) are the pipeline configuration files. They contain all the
necessary information to execute commands, use global variables and list expansions.

#### Name

Each fruit needs a name, which will identify the project the fruit belongs to.
To set the project name, use the following syntax:

```yaml
name: My Project Name
```

#### Description

The description field shall contain a longer description of the project, its goal
and the jobs defined in the fruit file. To set the description, use the following sytnax:

```yaml
desc: Create automated builds, package documentation, etc...
```

#### Global variables

It is possible to define global variables in the fruit file, which will be substituted during the yaml loading.

To create a global variable, add a new key-value pair to the list `glob`.

```yaml
glob:
  libpath: /usr/lib/
  binpath: $(libpath)bin
```

After the global variable is created it can be referenced with the sytax `$(<name>)`.

It's important to note, that global variables are propagated only downwards. As a consequence of this they affect:

- global variables define below,
- lists,
- step commands,
- step arguments.
