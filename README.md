## Project_Bonita_Studio
Below we will implement a procedure for ordering hospital sanitary equipment using the bonita BPM Studio program. More specifically, we created the model of the process of managing the orders of hospital health equipment, roles that enter the above process and the users for each role and we executed it.


# System design

In the first step, we created two pools for the correct implementation of the two different actions. The two diagrams are shown below. The first concerns orders for personal use material and orders for general purpose material. Regarding individual use, the procedure begins when the doctor creates the order (order creation). The order is then sent to the material department (receive order), where the responsible employee first sees the order and then checks the availability of each material (order check). Then, based on the availability of materials, two routes can be made. If there is availability in all materials then the materials are sent to the doctor who made the order (delivery material). Otherwise, the entire order is sent to the order check department, where it forwards it to the contractual supplier (order promotion). Finally, the contractual supplier receives the order (conclude order).

![image](https://user-images.githubusercontent.com/72653012/149651405-191954aa-dea5-4081-995d-7120e657aca0.png)

Similar to the above procedure, we implemented the procedure for ordering general purpose material with two differences. One is that the order is created by the nurse and the other is that if there is availability in all materials, the order is sent to the clinic chosen by the nurse.

![image](https://user-images.githubusercontent.com/72653012/149651425-38f8ae70-0d27-4628-a8c7-ff284a5153d3.png)


The next photo shows the business objects we used to implement the exercise. More specifically, the business object OrderCreation contains the details of the doctor or nurse who places the order, the necessary details of the order, such as: date, order number., Who will receive the order (patient or clinic name)…, and the materials and the quantities required by the order. Generally, the order form will list the details of who made the order and who will receive them (detailed business objects of the doctor, nurse, patient and clinic have been found that contain the basic information).
![image](https://user-images.githubusercontent.com/72653012/149651454-e3731e82-d350-4358-a844-b7cae7b9e1aa.png)

In the next step we implemented the appropriate contracts and the appropriate forms, which will be seen during the execution of the program. The next photo shows the usernames of the users for logging in and we have all used the default bpm code.
![image](https://user-images.githubusercontent.com/72653012/149651470-9263fbbe-d4cc-48a8-8219-43846802847a.png)

# Example

Below is an example for general use.
Clicking on the general purpose pool, as soon as we press run we will see the home page of the system.

![image](https://user-images.githubusercontent.com/72653012/149651490-265a0588-e068-463b-a474-8df6b5dd221d.png)

Upon entering the system, the nurse will be shown an order form and will have to fill in the order details, her own details and the details of the clinic so that they can be stored in the system, as shown in the example.

![image](https://user-images.githubusercontent.com/72653012/149651504-77131cfc-cb0f-465c-a40e-c14c66d23e7d.png)

![image](https://user-images.githubusercontent.com/72653012/149651508-f341171f-8026-4740-b533-5d37ffb8d2c0.png)
![image](https://user-images.githubusercontent.com/72653012/149651519-425eea49-aa77-4e84-9c5a-aef45483eda7.png)
![image](https://user-images.githubusercontent.com/72653012/149651526-d900ca72-89d6-4da3-9a10-ae4652a6984a.png)
After the nurse completes the order, she presses submit and the form is sent to the hardware department.
![image](https://user-images.githubusercontent.com/72653012/149651554-f1c1a8a4-8642-4def-b3f9-a09d37267177.png).
The employee of the department undertakes the work. First he fills in his details and then, after refreshing his page, the form appears to fill in if the materials are available or not.
Clarification: If all materials are available then select only one click on availability. If there is not at least one material then it creates only one availability and leaves it blank, as in the example.
![image](https://user-images.githubusercontent.com/72653012/149651580-97130f35-21b7-4b34-ab6d-1fe564198e58.png)
![image](https://user-images.githubusercontent.com/72653012/149651583-ae13b8c7-be1a-409f-aaa6-0ac4b2f7f687.png)
As soon as the employee of the hardware department presses submit, the order is sent to the procurement department. There the employee is asked to fill in his details, as well as the details of the supplier who is responsible for the supply of the relevant materials.
![image](https://user-images.githubusercontent.com/72653012/149651594-5eeb24c5-074f-4a84-be10-edb297e2a783.png)
![image](https://user-images.githubusercontent.com/72653012/149651598-72967793-e595-48b0-b199-fb6d82d9712b.png)
Finally, the supplier receives the order and sees the materials to be supplied.
![image](https://user-images.githubusercontent.com/72653012/149651613-aea4ab33-456a-4f21-b504-546cbaf82c94.png)






