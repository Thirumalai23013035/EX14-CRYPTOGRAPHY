# Experiment 14: Hash Algorithm
 
## Aim:
To implement the Hash Algorithm

## Algorithm: Simple Hash Computation and Verification

**Step-1**: Initialize `message` buffer, `hash` variable, and `receivedHash` array.  
**Step-2**: Prompt the user to enter a message and store it in `message`.  
**Step-3**: Calculate the hash using XOR and addition operations in `computeSimpleHash` function.  
**Step-4**: Display the computed hash in hexadecimal format.  
**Step-5**: Prompt the user to enter the received hash in hexadecimal format and store it in `receivedHash`.  
**Step-6**: Convert `receivedHash` from a hex string to an unsigned integer `receivedHashValue`.  
**Step-7**: Compare `hash` with `receivedHashValue`.  
**Step-8**: Print "Hash verification successful" if they match, otherwise print "Hash verification failed."  


## Code:
```
Name : THIRUMALAI V
Register no : 212223040229
```
```c
#include <stdio.h>
#include <string.h>

// Function to compute a simple hash using XOR and addition
void computeSimpleHash(const char *message, unsigned char *hash) {
    unsigned char temp = 0;

    // Simple hash computation: XOR and addition
    for (int i = 0; message[i] != '\0'; i++) {
        temp = temp ^ message[i]; // XOR each character
        temp += message[i];       // Add each character's value
    }

    // Store the result in the hash
    *hash = temp;
}

int main() {
    char message[256];        // Buffer for the input message
    unsigned char hash;       // Buffer for the hash (only 1 byte for simplicity)
    char receivedHash[3];     // Buffer for input of received hash (in hex format)

    // Step 1: Input the message
    printf("Enter the message: ");
    scanf("%s", message);

    // Step 2: Compute the simple hash
    computeSimpleHash(message, &hash);

    // Step 3: Display the computed hash in hexadecimal format
    printf("Computed Hash (in hex): %02x\n", hash);

    // Optional Step 5: Verify the hash
    printf("Enter the received hash (in hex): ");
    scanf("%s", receivedHash);

    // Convert received hash from hex string to an unsigned char
    unsigned int receivedHashValue;
    sscanf(receivedHash, "%02x", &receivedHashValue);

    // Compare the computed hash with the received hash
    if (hash == receivedHashValue) {
        printf("Hash verification successful. Message is unchanged.\n");
    } else {
        printf("Hash verification failed. Message has been altered.\n");
    }

    return 0;
}

```

## Output:
![Screenshot 2024-11-11 083840](https://github.com/user-attachments/assets/99aededd-6107-4364-bb9f-39041ae3c6e4)



## Result:
The program for Hash Algorithm was written and executed successfully


