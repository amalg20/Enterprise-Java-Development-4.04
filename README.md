# Enterprise-Java-Development-4.04

![picture](https://github.com/amalg20/Enterprise-Java-Development-4.04/assets/145042005/b79e2edf-4f3d-4daa-be57-1621e079dae3)



# 1. Some information about the program 

##  ِA. Did you use the same type of route to update patient information as to update an employee’s department?

No, the paths for the given routes for changing patient data and altering a worker's department are distinct and use separate HTTP methods (PUT and PATCH).

**-Update Patient Information using PUT:**

HTTP Method: PUT

Route: /api/patients/{id}

Path Variable: {id} represents the unique identifier of the patient

![photo_2023-10-17_20-53-10](https://github.com/amalg20/Enterprise-Java-Development-4.04/assets/145042005/ff75dbaf-d104-44a2-ac73-e6fc601dfc95)


 
**-Update Employee's Department using PATCH:**

HTTP Method: PATCH

Route: /api/employees/department/{id}

Path Variable: {id} represents the unique identifier of the employee.

![photo_2023-10-17_20-53-10](https://github.com/amalg20/Enterprise-Java-Development-4.04/assets/145042005/ff75dbaf-d104-44a2-ac73-e6fc601dfc95)



## B. Why did you choose the selected strategy?

**-Using PUT, update the patient's information:-**

the cause: PUT is frequently used to completely update or replace a resource. It implies that the client must deliver the resource's entire updated representation.
PUT is a good option because updating patient information frequently involves providing the entire set of patient details.
*Path Structures:' /api/patients/{id}' suggests updating a specific patient identified by {id}.*


**-Using PATCH, update the department of the employee:-**

the cause: PATCH is made for partial updates, in which the client provides only the adjustments that must be made to the resource.
PATCH is an appropriate option since updating an employee's department may include modifying a specific property without sending the full employee resource.
Path Structures: '/api/employees/department/{id}' suggests updating the department of a specific employee identified by {id}, treating the department as a subresource of an employee.

## C. What are the advantages and disadvantages of the strategies you chose for creating these routes?
**Update Patient Information using PUT:**

*Advantages:*

 Using PUT clearly communicates the intent to perform a complete update or replacement of the resource. This aligns well with scenarios where clients are expected to provide the entire updated representation.
  
*Disadvantages:*

If your application frequently uses partial updates, using PUT might not be in line with the semantics of partial updates.
**Update Employee's Department using PATCH:**


*Advantages:*

is made to support partial updates, enabling the sending of only the resource-specific modifications. When only a tiny fraction of a resource is being updated, this may be more bandwidth-efficient.

*Disadvantages:*

As the changes must be merged with the existing resource, handling partial updates may add extra complexity on the server side.

## D. What is the cost-benefit between using PUT and PATCH?
**PUT (Complete Update)**

*Benefit:*

 Idempotence
PUT has the advantage of being idempotent. Making the same request more than once has the same result as making it once. This guarantees regularity and dependability.

*Costs:*

Overhead for Partial Updates:-
Cost: If clients only want to update specific fields and are required to send the complete resource representation, it can lead to increased bandwidth usage and overhead.


**PATCH (Partial Update)**

*Benefits:*

Partial Update Efficiency: PATCH is designed for partial updates, allowing clients to communicate only the changes that need to be applied to the resource. For updates affecting a tiny percentage of the resource, this can be more bandwidth-efficient.

*Costs:*

Potential for Complexity: Cost: Handling partial updates might introduce additional complexity on the server side, as it needs to merge the changes with the existing resource.

# 2. Reference
1. https://www.linkedin.com/pulse/whats-difference-between-post-put-patch-restful-apis-okpala







