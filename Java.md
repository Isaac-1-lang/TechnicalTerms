1. Access Modifiers
Modifier	Accessible in Class	Package	Subclass	Outside Package
private	                 ✅   	❌	     ❌	     ❌  
default (no modifier)	   ✅	    ✅	     ❌      ❌
protected	               ✅   	✅	     ✅	     ❌
public	                 ✅	    ✅	     ✅	     ✅

Protected: Very crucial when you want subclasses and package classes to access fields or methods.

Default: Works within the class and package only. Subclasses outside the package cannot access it.

2. Encapsulation

Encapsulation is the practice of restricting direct access to class fields and exposing controlled access through methods.

Getters: Retrieve field values.

Setters: Modify field values.

Why prefer setters over constructors?

Validation: Ensure only valid data is set.

Readability: Makes code easier to understand and maintain.

Flexibility: Allows changing values after object creation without modifying the constructor.

Consistency: Useful in frameworks like Spring/JavaBeans.

Note: Sometimes getters come before setters depending on your constructor style (default or parameterized).

3. Constructors

Default constructor: Automatically created if no constructor is explicitly defined.

Parameterized constructor: Allows initializing object fields at creation.

Order of getters/setters: Optional; can be placed before or after constructors depending on coding style.

4. toString() Method

Used to make objects human-readable when printed.

Without overriding toString(), printing an object shows the class name + hashcode (not user-friendly).

@Override
public String toString() {
    return "Person{name='" + name + "', age=" + age + "}";
}

5. Abstract Classes vs Interfaces
Feature	Abstract Class	Interface
Can have fields	✅	❌ (only constants)
Can have constructors	✅	❌
Methods	Can have concrete & abstract	Only abstract (until Java 8; default methods allowed)
Extending/Implementing	extends	implements

Abstract classes: Extended by subclasses.

Interfaces: Implemented by classes.

6. Exceptions
IllegalArgumentException

Thrown when a method receives an argument that is inappropriate or invalid.

Unchecked exception (like IndexOutOfBoundsException, NullPointerException).

Example:

public void setAge(int age) {
    if (age < 0) throw new IllegalArgumentException("Age cannot be negative");
    this.age = age;
}


Checked vs Unchecked Exceptions:

Checked: Must be declared/handled (IOException, SQLException).

Unchecked: Runtime exceptions, optional to handle (IllegalArgumentException, NullPointerException).

7. Java File Creation Issue

"Failed to create a Java file in every found file" usually happens due to:

Permissions issue.

Incorrect path.

File already exists.

IDE or compiler misconfiguration.

✅ Summary / Key Tips

Always encapsulate fields (use getters & setters).

Use setters for validation.

Override toString() for readability.

Know the difference: abstract classes (extends) vs interfaces (implements).

Use protected wisely for inheritance across packages.

Remember: IllegalArgumentException is unchecked.

Constructors are for initialization; setters are for controlled updates.

Pay attention to IDE errors when creating files—they often indicate permissions or path issues.
