# todo

track your todo lists in your terminal

## Installation

### Requirements

- crystal (see the shards.yml file) (tested with v0.27.0)
- shards

### Build

    make

## Usage

    todo # list the tasks
    todo -l listX # list (-l = list selection) the tasks of a list
    todo --rm ID # remove a task
    todo --date DATE an example of content for a task # add a new task

    Usage: todo [arguments]
        -a=ID, --archive=ID              Move to archive
        -u=ID, --update=ID               Update the task ID
        -r=ID, --remove=ID               Delete the task ID
        -d=DATE, --date=DATE             Set the date
        --clear-all                      Remove everything in the list
        -l=NAME, --list=NAME             Filter with the list NAME
        --directory=PATH                 Change the directory of the todolist
        -s, --sort                       Sort by date (by default)
        -i, --sort-id                    Sort by id
        -h, --help                       Show this help

### Date parsing
There are several type of date format which are parsed automatically:

- ``[Y]/<M>/<D>``: classic date format
- ``D+<n>``: where n is the amount of days before the task ends

## Configuration

### Hooks
I you want someting to get executed right after or before an operation,
you can setup some hooks.
Write a yaml file `~/.config/todorc` with the following structure:

```yaml
hooks:
  before_load:
    - some command to execute
    - an other command
  after_load:
  before_add:
  after_add:
  before_list:
  after_list:
  before_rm:
  after_rm:
  before_update:
  after_update:
  before_archive:
  after_archive:
  before_clear_all:
  after_clear_all:
  before_save:
  after_save:
```

Each hooks can take several parameters:

- `mode`: current operation
- `date`: date of the task
- `id`: id of the task
- `list_name`: name of the list of task
- `dir_name`: directory where the task is registered
- `msg`: body on the task
- `sort`: type of sort (date, id, ...)


## Development

TODO: Write development instructions here

## Contributing

1. Fork it ( https://github.com/Nephos/todo/fork )
2. Create your feature branch (git checkout -b my-new-feature)
3. Commit your changes (git commit -am 'Add some feature')
4. Push to the branch (git push origin my-new-feature)
5. Create a new Pull Request

## Contributors

- [Nephos](https://github.com/Nephos) Arthur Poulet - creator, maintainer
