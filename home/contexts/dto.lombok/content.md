# Lombok Guidelines

## Usage
Use Lombok annotations to reduce boilerplate for all Java beans DTO. 

- Use lombok for all DTO for incoming REST request inputs and response outputs.
- Use lombok for all DTO with Spring Repository and manual SQL persistence code.
- Use Jakarta for DTO input validations as needed.

## Coding Guidelines
As a coding standard, we require the following Lombok annotations upon
the DTO class declarations:

- @Data 
- @Builder 
- @NoArgsConstructor
- @AllArgsConstructor


### Example code:
The code below shows a coding standard compliant example of a POST input DTO for a REST API.

```Java
package com.rcl.fubar; 

import lombok.Data;
import lombok.NoArgsConstructor;
import lombok.AllArgsConstructor;
import lombok.Builder;

import jakarta.validation.constraints.Email;
import jakarta.validation.constraints.NotBlank;
import jakarta.validation.constraints.Size;

@Data  
@NoArgsConstructor 
@AllArgsConstructor 
@Builder 
public class UserRequest {

    @NotBlank(message = "Name is required")
    @Size(max = 50, message = "Name must be less than 50 characters")
    private String name;

    @Email(message = "Invalid email format")
    @NotBlank(message = "Email is required")
    private String email;
}
```
