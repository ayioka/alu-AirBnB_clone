# alu-AirBnB
An AirBnB clone.

## Description 🏠
HBnB is a complete web application that integrates database storage, a back-end API, and front-end interfacing, mimicking the core functionality of AirBnB. This project is the first step towards building a full web application: an AirBnB clone. The initial phase focuses on developing a custom command-line interface for data management and base classes for data storage.

## Usage 💻
The console operates both in interactive and non-interactive modes, similar to a Unix shell. It prompts with `(hbnb)` and waits for user input.

### Command Examples:
| Command | Example |
|---------|---------|
| Run the console | `./console.py` |
| Quit the console | `(hbnb) quit` |
| Display help for a command | `(hbnb) help <command>` |
| Create an object (prints its id) | `(hbnb) create <class>` |
| Show an object | `(hbnb) show <class> <id>` or `(hbnb) <class>.show(<id>)` |
| Destroy an object | `(hbnb) destroy <class> <id>` or `(hbnb) <class>.destroy(<id>)` |
| Show all objects or instances of a class | `(hbnb) all` or `(hbnb) all <class>` |
| Update an attribute of an object | `(hbnb) update <class> <id> <attribute name> "<attribute value>"` or `(hbnb) <class>.update(<id>, <attribute name>, "<attribute value>")` |

### Non-interactive mode example:
```bash
$ echo "help" | ./console.py
(hbnb)
```
i
### Documented commands:
- EOF
- all
- count
- create
- destroy
- help
- quit
- show
- update

## Models 🐧
The `models` folder contains all the classes used in the project.

| File | Description | Attributes |
|------|-------------|------------|
| base_model.py | BaseModel class for all other classes | `id`, `created_at`, `updated_at` |
| user.py | User class for future user information | `email`, `password`, `first_name`, `last_name` |
| amenity.py | Amenity class for future amenity information | `name` |
| city.py | City class for future location information | `state_id`, `name` |
| state.py | State class for future location information | `name` |
| place.py | Place class for future accommodation information | `city_id`, `user_id`, `name`, `description`, `number_rooms`, `number_bathrooms`, `max_guest`, `price_by_night`, `latitude`, `longitude`, `amenity_ids` |
| review.py | Review class for future user/host review information | `place_id`, `user_id`, `text` |

## File storage 🛄
The `engine` folder manages the serialization and deserialization of all the data in JSON format.

The `FileStorage` class in `file_storage.py` handles this process:
1. Object -> `to_dict()` -> Dictionary -> JSON dump -> JSON string -> File
2. JSON string -> JSON load -> Dictionary -> Object

The `__init__.py` file contains the instantiation of the `FileStorage` class as `storage` and calls `reload()` to automatically reload serialized data upon initialization.

## Tests 📏
All the code is tested using the `unittest` module. Tests are stored in the `tests` folder.

To run the entire test suite:
```bash
$ python3 -m unittest discover tests
```

To run a single test file:
```bash
$ python3 -m unittest tests/test_console.py
```

## Authors ✒️

Shem Ayioka <s.ayioka@alustudent.com> 
