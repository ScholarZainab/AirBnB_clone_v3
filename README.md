AirBnB Clone - The Console
The console is the first segment of the AirBnB project at Holberton School that introduces fundamental concepts of higher-level programming. The ultimate goal of the AirBnB project is to deploy a simple copy of the AirBnB website (HBnB). This segment involves creating a command interpreter to manage objects for the AirBnB (HBnB) website.

Functionalities of this command interpreter:
Create a new object (e.g., a new User or a new Place)
Retrieve an object from a file, a database, etc.
Perform operations on objects (count, compute stats, etc.)
Update attributes of an object
Destroy an object
Table of Contents
Environment
Installation
File Descriptions
Usage
Examples of Use
Bugs
Authors
License
Environment
This project is interpreted and tested on Ubuntu 14.04 LTS using Python 3 (version 3.4.3).

Installation
Clone this repository: git clone "https://github.com/alexaorrico/AirBnB_clone.git"
Access the AirBnB directory: cd AirBnB_clone
Run hbnb interactively: ./console and enter commands
Run hbnb non-interactively: echo "<command>" | ./console.py
File Descriptions
console.py - The console contains the entry point of the command interpreter. The commands currently supported by this console include:

EOF - exits the console
quit - exits the console
<emptyline> - overwrites the default empty line method and does nothing
create - creates a new instance of BaseModel, saves it (to the JSON file), and prints the ID
destroy - deletes an instance based on the class name and ID (saves the change to the JSON file)
show - prints the string representation of an instance based on the class name and ID
all - prints the string representation of all instances, based on the class name or not
update - updates an instance based on the class name and ID by adding or updating attributes (saves the change to the JSON file)
models/ directory contains classes used for this project:
base_model.py - The BaseModel class from which future classes will be derived

def __init__(self, *args, **kwargs) - Initialization of the base model
def __str__(self) - String representation of the BaseModel class
def save(self) - Updates the attribute updated_at with the current datetime
def to_dict(self) - returns a dictionary containing all keys/values of the instance
Classes inherited from BaseModel:

amenity.py
city.py
place.py
review.py
state.py
user.py
/models/engine directory contains the File Storage class that handles JSON serialization and deserialization:
file_storage.py - Serializes instances to a JSON file and deserializes them back to instances

def all(self) - returns the dictionary __objects
def new(self, obj) - sets obj in __objects with the key <obj class name>.id
def save(self) - serializes __objects to the JSON file (path: __file_path)
def reload(self) - deserializes the JSON file to __objects
/tests directory contains all unit test cases for this project:
test_models/test_base_model.py - Contains the TestBaseModel and TestBaseModelDocs classes

TestBaseModelDocs class:
def setUpClass(cls) - Set up for the doc tests
def test_pep8_conformance_base_model(self) - Test that models/base_model.py conforms to PEP8
def test_pep8_conformance_test_base_model(self) - Test that tests/test_models/test_base_model.py conforms to PEP8
def test_bm_module_docstring(self) - Test for the base_model.py module docstring
def test_bm_class_docstring(self) - Test for the BaseModel class docstring
def test_bm_func_docstrings(self) - Test for the presence of docstrings in BaseModel methods
TestBaseModel class:
def test_is_base_model(self) - Test that the instantiation of a BaseModel works
def test_created_at_instantiation(self) - Test that created_at is a public instance attribute of type datetime
def test_updated_at_instantiation(self) - Test that updated_at is a public instance attribute of type datetime
def test_diff_datetime_objs(self) - Test that two BaseModel instances have different datetime objects
test_models/test_amenity.py - Contains the TestAmenityDocs class

TestAmenityDocs class:
def setUpClass(cls) - Set up for the doc tests
def test_pep8_conformance_amenity(self) - Test that models/amenity.py conforms to PEP8
def test_pep8_conformance_test_amenity(self) - Test that tests/test_models/test_amenity.py conforms to PEP8
def test_amenity_module_docstring(self) - Test for the amenity.py module docstring
def test_amenity_class_docstring(self) - Test for the Amenity class docstring
test_models/test_city.py - Contains the TestCityDocs class

TestCityDocs class:
def setUpClass(cls) - Set up for the doc tests
def test_pep8_conformance_city(self) - Test that models/city.py conforms to PEP8
def test_pep8_conformance_test_city(self) - Test that tests/test_models/test_city.py conforms to PEP8
def test_city_module_docstring(self) - Test for the city.py module docstring
def test_city_class_docstring(self) - Test for the City class docstring
test_models/test_file_storage.py - Contains the TestFileStorageDocs class

TestFileStorageDocs class:
def setUpClass(cls) - Set up for the doc tests
def test_pep8_conformance_file_storage(self) - Test that models/file_storage.py conforms to PEP8
def test_pep8_conformance_test_file_storage(self) - Test that tests/test_models/test_file_storage.py conforms to PEP8
def test_file_storage_module_docstring(self) - Test for the file_storage.py module docstring
def test_file_storage_class_docstring(self) - Test for the FileStorage class docstring
test_models/test_place.py - Contains the TestPlaceDocs class

TestPlaceDocs class:
def setUpClass(cls) - Set up for the doc tests
def test_pep8_conformance_place(self) - Test that models/place.py conforms to PEP8
def test_pep8_conformance_test_place(self) - Test that tests/test_models/test_place.py conforms to PEP8
def test_place_module_docstring(self) - Test for the place.py module docstring
def test_place_class_docstring(self) - Test for the Place class docstring
test_models/test_review.py - Contains the TestReviewDocs class

TestReviewDocs class:
def setUpClass(cls) - Set up for the doc tests
def test_pep8_conformance_review(self) - Test that models/review.py conforms to PEP8
def test_pep8_conformance_test_review(self) - Test that tests/test_models/test_review.py conforms to PEP8
def test_review_module_docstring(self) - Test for the review.py module docstring
def test_review_class_docstring(self) - Test for the Review class docstring
test_models/test_state.py - Contains the TestStateDocs class

TestStateDocs class:
def setUpClass(cls) - Set up for the doc tests
def test_pep8_conformance_state(self) - Test that models/state.py conforms to PEP8
def test_pep8_conformance_test_state(self) - Test that tests/test_models/test_state.py conforms to PEP8
def test_state_module_docstring(self) - Test for the state.py module docstring
def test_state_class_docstring(self) - Test for the State class docstring
test_models/test_user.py - Contains the TestUserDocs class

TestUserDocs class:
def setUpClass(cls) - Set up for the doc tests
def test_pep8_conformance_user(self) - Test that models/user.py conforms to PEP8
def test_pep8_conformance_test_user(self) - Test that tests/test_models/test_user.py conforms to PEP8
def test_user_module_docstring(self) - Test for the user.py module docstring
def test_user_class_docstring(self) - Test for the User class docstring
Examples of Use
python
Copy code
vagrant@AirBnB_clone$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  all  create  destroy  help  quit  show  update

(hbnb) all MyModel
** class doesn't exist **
(hbnb) create BaseModel
7da56403-cc45-4f1c-ad32-bfafeb2bb050
(hbnb) all BaseModel
[[BaseModel] (7da56403-cc45-4f1c-ad32-bfafeb2bb050) {'updated_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772167), 'id': '7da56403-cc45-4f1c-ad32-bfafeb2bb050', 'created_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772123)}]
(hbnb) show BaseModel 7da56403-cc45-4f1c-ad32-bfafeb2bb050
[BaseModel] (7da56403-cc45-4f1c-ad32-bfafeb2bb050) {'updated_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772167), 'id': '7da56403-cc45-4f1c-ad32-bfafeb2bb050', 'created_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772123)}
(hbnb) destroy BaseModel 7da56403-cc45-4f1c-ad32-bfafeb2bb050
(hbnb) show BaseModel 7da56403-cc45-4f1c-ad32-bfafeb2bb050
** no instance found **
(hbnb) quit
Bugs
No known bugs at this time.

Authors
Zainab Akinola - https://github.com/ScholarZainab /https://twitter.com/zainab297086931
License
Public Domain. No copyright protection.
