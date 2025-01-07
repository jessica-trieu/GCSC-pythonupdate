# Google Cybersecurity Certificate Project: Update a File Through Python Algorithim
## Description
In this project, I am a security analyst working for a healthcare company who needs to review and update the list of employees allowed to personal patient records. The allowed employees are able to access the records if their IP addresses are approved to connect to the subnetwork. There is also a list of employees that need to be removed from the allowed list. 
To update the list, I would need to use Python to create an algorithm.

## Open the file that contains the allow list
First, I assigned the file name ``“allow_list.txt”`` to the ``import_file`` variable. 
![image](https://github.com/user-attachments/assets/d698fc11-46e9-49ae-941b-84d62291b384)

Then I created a ``with`` statement which will import the list into the ``file`` variable. 
![image](https://github.com/user-attachments/assets/e8dfa095-f3be-4ac6-8e95-13a7999aba35)

When writing the header of my ``with``  statement, I used the ``import_file`` variable as the first parameter of my ``open`` function and ``“r”`` as my second parameter, which indicates I would like to read the file. When you open a file using ``with open()``, you must provide a variable to store the output. I can do this through the keyword ``as`` followed by this variable name, in this case `file` . The end of the header needs to have a (``:``). 

## Read the file contents

After constructing the header of the with statement, for the body, I append the ``.read()`` method to the ``file`` variable from the `with` statement. This converts the data into string. I also assign the output to the variable ``ip_addresses``.
![image](https://github.com/user-attachments/assets/4d3038fb-783c-4e03-8f97-06a71d550922)

 In summary, this code reads the contents of the "allow_list.txt" file into a string format that allows me to later use the string to organize and extract data in my Python program.

## Convert the string into a list
The file currently displays its contents as string data, listing each element on a new line. In order to remove certain IP addresses, I need convert the string data to list data. To do that, I append the ``.split() `` method after ``ip_addresses``. The default separtor for `split()` is any whitespace between the elements in the string data. I then assign the output again to ``ip_addresses`` so that when I display it with a `print()` function, the contents will show as list data. 

![image](https://github.com/user-attachments/assets/a42c6246-2105-4fc6-b445-5cb3dce8f7b3)

## Iterate through the remove list

Now that the data is formated as list data, I can create a `for` loop that will iterate through the list of IP addresses to be removed (`remove_list`), find the IP addresses that are in both `remove_list` and the list of allowed IP addresses (`ip_addresses`), and remove the matching IP addresses from `ip_addresses`. 

![image](https://github.com/user-attachments/assets/4582ffb0-ad32-472c-a1e2-5037e90ca175)

The `for` loop in Python runs a code repeatedly until specific conditions are met. The ``for`` keyword starts the for loop. `in` indicates to iterate through the sequence ``ip_addresses`` and assign each value to the loop variable, ``element``. 



## Remove IP addresses that are on the remove list
The next line is the body of the ``for`` loop. The body will be a conditional statement. Using ``if element in ip_addresses``:, I set the condition that if the ``element`` variable in `remove_list` is also in ``ip_addresses``, then an action needs to be done.
![image](https://github.com/user-attachments/assets/687631a3-77c8-4aa6-a047-096214ac5e2b)

In the body of my conditional statement, I append the ``remove`` method, with the ``element`` variable as my argument, after ``ip_addresses``. The ``remove`` method will tell Python to remove that element from ``ip_addresses``. 

## Update the file with the revised list of IP addresses 

Now that the IP addresses that needed to be removed were removed, it is time to update the original file with the new list of elements. To do so, I had to convert the contents of ``ip_addresses`` from list data to string data. This is necessary because ``ip_addresses`` must be in string format when used inside the ``with`` statement to rewrite the file. 
![image](https://github.com/user-attachments/assets/2c16efca-1c5b-49dd-ad39-a5a902b3bacb)

I use the ``.join()`` method with ``ip_addresses`` as my argument. ``“\n“`` is before “.join” because I want to separate each element in the string on a new line. (Otherwise it will combine it all into one long string.) I reassign the output to the variable `ip_addresses`.

Next I create a `with` statement. 

![image](https://github.com/user-attachments/assets/b14abbc2-7a99-4472-b223-8663b3232828)

I used ``with open()``, using ``import_file`` (the file I want to open) as my first argument and ``“w”`` as my second argument to indicate that I would like to overwrite the file. For the body of my `with` statement, I append ``file`` with ``.write(ip_addresses)``. This will replace the original contents in ``“allow_list.txt”`` with the updated content.

## Summary
In this activity, I demonstrated the ability to create an algorithm that removes elements from a file, specifically the IP addresses in ``remove_list`` from the file ``“allow_list.txt”``.Using the with ``open()`` function, I was able to access the file’s content, convert it into list data using ``.split()``, and  remove the IP addresses listed in the ``remove_list``. The algorithm used a ``for`` loop to go through the ``remove_list``, and used ``.remove()`` to remove the IP addresses no longer allowed on the subnetwork for restricted content. Using ``.join()``, I was able to convert the list back into string. Then I took the updated content and replaced the contents of the original file with the revised list.
