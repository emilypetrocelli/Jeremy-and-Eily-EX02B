# Normalization Process for Vet Offices

## Step 1: Identifying Dependencies and Candidate Keys
Functional Dependencies

-->PetName-(PetID, PetBreed, PetDOB, OwnerLastName, OwnerFirstName,OwnerPhone, OwnerEmail)
-->OwnerEMail-(OwnerFirstName, OwnerLastName, OwnerPhone)
-->OwnerPhone-(OwnerLastName,OwnerFirstName,OwnerPhone)

Canidate Keys- PetName

Is every determinant a candidate key?
No, OwnerEmail and OwnerPhone are NOT candidate keys.

## Step 2: Break into two relations
1. Owner
2. Pet

-->OWNER-(OwnerLastName, OwnerFirstName, OwnerPhone, OwnerEmail)
-->PET-(PetID, PetType, PetBreed, PetDOB)

### Step 3: List the functional dependencies and the candidate keys for OWNER 
-->OwnerEmail-(OwnerLastName,OwnerFirstName,OwnerPhone)
-->OwnerPhone-(OwnerLastName,OwnerFirstName,OwnerEmail)

OWNER Candidate Keys- OwnerEmail,OwnerPhone

Is every determinant a candidate key? YES, OwnerEmail and OwnerPhone are both candidate keys, normalization process is complete. 

### Step 3: List the funtional dependencies and candidate keys for PET
-->PetName(PetTYpe, PetBreed,PetDOB,PetBreed,OwnerPhone)

PET-Candidate Keys-PetName

Is every Determinant a candidate key? YES, PetName is a candidate key, normalization process is complete. 

#### We can use OwnerEmail as a primary key giving us:
-->Owner(OwnerPhone,OwnerLastName,OwnerFirstName,OwnerEmail)

-->Pet(PetName,PeType,PetDOB,PetBreed,OwnerEmail)

##### Final Normalization Relations
-->OWNER(OwnerPhone,OwnerLastName,OwnerFirstName,OwnerEmail)

-->PET(PetName,PetType,PetBreed,PetDOB,OwnerPhone)
