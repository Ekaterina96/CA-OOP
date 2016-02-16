
The Staff class should provide the following instance-level methods as a minimum:
1. A constructor, which generates a Staff instance with initial details of the staff member passed
as arguments (forename, surname, ID, address)
2. A method that takes a single Module instance as an argument, and appends this to the list of
modules that this Staff member lectures on (maintained by the Staff instance).
3. A method that takes a single Module instance as an argument, and removes this module from the list of modules that this Staff member lectures on. If the staff member has not recorded that it lecturers on the module provided, it should return false. Otherwise it should return true when it has successfully removed the module.
4. A method that takes a single Module instance as an argument, and appends this to the list of modules that this Staff member coordinates however it should ensure that it does not generate duplicates, returning false if this is attempted (returning true otherwise).
5. A method that takes a single Module instance as an argument, and removes this from the list of modules that this Staff member coordinates. If the staff member has not recorded that it coordinates the Module provided as an argument, it should return false. Otherwise it should return true when it has successfully removed the Module.
6. A method that returns the total number of modules a lecturer lectures on.
7. A method that returns the total number of modules a lecturer coordinates.
8. An equals method, with the signature: public boolean equals(Object obj). This must return true if the staff details match those of the Object argument, otherwise false.1

The Student class should provide the following instance-level methods as a minimum: 1Note: we will cover writing equals methods in the second lecture of week 4
1. A constructor, which generates a Student instance with initial details of the student passed as arguments (forename, surname, ID, address)
2. A method that takes a single Module instance as an argument, and appends this to the list of modules that this Student is enrolled on, if enrolling does not cause them to exceed 120 credits in total. If the student is successfully enrolled it should return true, otherwise it should return false. It should not allow the enrolment on duplicate modules (i.e. the same module more than once), and return false if this action is attempted.
3. A method that takes a single Module instance as an argument, and removes this from the list of modules that this Student is enrolled on. If this student has not recorded that it is enrolled on the Module given, it should return false. Otherwise it should return true when it has successfully removed the Module.
4. A method to return the total number of credits the student is currently enrolled on.
5. An equals method, with the signature: public boolean equals(Object obj). This must
return true if the student details match those of the Object argument, otherwise false.

The Module class should provide the following instance-level methods as a minimum:
1. A constructor, which generates a Module instance, with initial details of the Module passed as arguments (code, name, number of credits)
2. A method that takes a single Staff instance as an argument, and appends this to the list of lecturers on this module. It should also update the Staff instance argument accordingly to reflect its new role. It should not allow duplicates, returning false if a duplicate Staff entry is attempted, true otherwise.
3. A method that takes a single Staff instance as an argument, and removes this from the list of module lecturers. It should also update the Staff instance argument accordingly. If the Staff member was not recorded as a module lecturer it should return false, otherwise it should return true.
4. A method that takes a single Staff instance as an argument, and sets this as the module coordinator. If there is an existing module coordinator recorded, then this member should be first updated, so that its state reflects that it is no longer a coordinator of the module, before the new coordinator is set. The new coordinator (the Staff instance argument) should be updated accordingly to reflect its new role.
5. A method that takes a single Student instance as an argument and enrols it on the module. It should ensure that the same student is not enrolled more than once on a particular module, and that they will not exceed 120 credits if enrolled. If the student is already enrolled, or enrolling will cause them to exceed 120 credits, then this method should return false, otherwise it should return true and add the student to the list of student on the module (adding them to the student list for the module, and update the state of the Student instance to reflect its new enrolment).
6. A method that returns the total number of credits for the module.
7. An equals method, with the signature: public boolean equals(Object obj). This must
return true if the module details match those of the Object argument, otherwise false.
Note that many of the Module methods change not only the state of the module instance they are called on, but also the state of the argument (i.e. Staff instance or Student instance). Think carefully about how you will use the methods defined in these other classes to enable this to happen. You may only use other classes available in the default (java.lang) package for this CA (alongside the ObjectArrayList class provided).
Finally the ObjectArrayList class is rather inefficient in how it manages resizing the array it contains. Your team should consider how this might be improved. On no more than one side of A4 detail how you would improve this aspect of the provided class.
