---
date: 2025-11-12
Prof: Tanuj Karia
aliases:
  - Advanced Python Programming
---
## Basic Programming Principles
- Single-Responsibility Principle (SRP)
	A function (or a class, module) should be responsible for a single part of the functionality
- Don't Repeat Yourself (DRY)
	Code should not be duplicated. If you need code more than once, write a function. 
- Separation of Concerns (SoC)
	Each part of your program should focus on a single aspect or concern of the system. Different parts of the program should only be coupled loosely. 
- You aren't gonna need it (YAGNI)
	Don't write code for hypothetical requirements. Focus on current requirements. Add features to code when they are needed. 


## Managing imports, packages, virtual environments
### Import sources
Why import: 
   the less commands Python has to keep track of, the faster it is!

Package types:
- Python standard library
	*import without other action*
- External packages managed via **pip** (*the Package Installer for Python*)
	pip install \<package>
	pip install \<package>\==\<version>
		`pip instal numpy==1.19.5`
	pip list
		*list installed packages*
- Our own packages or modules

### Virtual environments
allow separate management of package dependencies.
avoid package conflicts and ensure consistency.
![[eff220619c47b605c8967b7ca8327a89edefb62d09c86fd41f249d53a600a21d.png]]
- Creating the environment
	`>> python -m venv <environment name>`
- Activate the environment
	`>> <environment name>/Scripts/activate`
- Use pip in the environment
	`(<environment name>)>> pip install numpy`
	requirements file: (-r)
	`(<environment name>)>> pip install -r requirements.txt`
- Deactivate the environment
	`(<environment name>)>> deactivate`

## Managing Multiple Modules
Challenges arise for code management: 
- Readability
- Maintainability
- Reusability
- Namespace management

Organize your projects into:
- Modules (python files)e
- **Packages** (python folders with an ==\_\_init\_\_.py== file)   !! remember 2\_
	![[7675e95cef4b659ebf998ada13f1c26b3f721d8674f8f06a896f60fbeffea01b.png]]
	```
	# In module "main.py"
	import flowsheet
	import properties. thermodynamics
	from properties. reactions import WGShift, Syngas
	```


## Basic Object-Oriented Programming
Object-Oriented Programming (**OOP**): 
	A programming paradigm based on the concept of "**objects**":
	"Is something": has a predefined conceptual data and behavioural structure - **class**.
	"Has something": Contains and encapsulates data related to its meaning - **attributes**. 
	"Does something": Has associated functionality operating on its data - **methods**. 

- **Class**:
	A blueprint for creating objects. 
	Defines attributes(data) and methods(functions)
	**Object** is an instance of a class. Contains actual data and can use methods defined in the class. 
	\**An object can have other objects as attributes.*

- ==Define a class==:
	```
	class Vessel:
		```
		A class to represent a cylindrical vessel and calculate its volume
		Attributes:
			height(float)
			diameter(float)
		Methods:
			calculate_volume
		```
		def __init__(self, height:float, diameter:float):
		```The constructor with instructions for creating a class```
		self.diameter=diameter
		self.height=height
		
		def calculate_volume(self)->float:
		volume=self.height*self.diameter**2*math.pi/4
		return volume
	```
	- **Constructor**: 
		Define a constructor to your class with the "==\_\_init__==". 
		It sets the attributes to an initial value. 
		It defines further instructions for the instantiation of a new class.
	- **self**:
		A reference to the object itself used to retrieve attributes and other methods.
	- **Method**:
		Add methods to give your class functionality. 


- ==Use a class==:
	```
	my_vessel=Vessel(1.2,3.5)
	print(my_vessel)  #<_main_.Vessel object at 0x0000020..>
	print(my_vessel.diameter) #3.5
	print(my_vessel.calculate_volume()) #11.54535300..
	```
	- **Constructor**: instantiate your class by calling the constructor of the class. Store a reference to the new object like a variable. 
	- **Attributes/Methods**: use dot-notation to access attributes or call methods of the class. 
	- **self**: the "self" argument is ==not explicit specified==. 


- Class inheritance
	![[a8129f4eb06bde9dd67cf58ebcda5491d6079625ac7f1f43b5e78b53e787424e.png]]
	
- ==Define a child class==:
	```
	class Reactor(Vessel):
	```Reactor class that is a vessel and also stores temperature.```
	
	def __init__(self, height:float, diameter:float, temperature:float):
	super()._init_(height,diameter)
	self.temperature=temperature
	
	def get_temperature(self):
	return self.temperature
	```
	- **class Child(Parent)**: 
		Name of parent after the class name indicates inheritance.
	- **super()**: 
		In new constructor, first call parent constructor by referencing parent with “==super()==”. Then, add further functionality.
	- **Methods**: Change the functionality of parent methods (overriding) or define new methods.

- ==Use a child class==:
	```
	my_reactor=Reactor(1.2,3.5,350)
	print(my_reactor.diameter)
	print(my_reactor.calculate_volume())
	print(my_reactor.temperatur)
	print(my_reactor.get_temperature())
	```


## Unit Testing
- **Testing code**
	define runtime environment, (example) code inputs, and expected outputs
	-> execute code 
	-> compare output against expected output 
	![[b172f0d0ba85a152af0dae408c612d96afa155889fb232806f9076bae3789751.png]]
	- **assert**: 
		compares output against expected outputs.
		does nothing if condition holds, otherwise, throws an AssertionError with this error message.
		*\* A test can have multiple assert-statements to test for several cases. 
		However, it is best to separate meaningful test cases into separate functions.* 
	
	Where to put:
	 **Test dictionary** with the same structure. Module names are the same with "test_". ![[19e2e6adb80f7fddc8558241498b3705e62b72a008b7548a35b949a3702aeb27.png]]
	 \* Each function or class method has at least one (typically more) corresponding test function. 
	
	
- **pytest**: automatically finds testing functions, helps to organize and run them
	`>> pytest` 
		(run pytest runs **all** tests in the project)
	`>> pytest tests/test_reynolds_number.py` 
		(run tests in a specific module by running)
