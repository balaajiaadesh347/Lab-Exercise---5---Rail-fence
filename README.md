# Lab-Exercise---5---Rail-fence
## Aim
To develop a simple C program to implement Rail Fence Cipher.
## Procedure 
1. Design of Rail Fence Cipher algorithm.
2. Implementation using C or Python code.
3. Testing algorithm with different key values.
4. In the Rail Fence Cipher, the plaintext is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail.
5. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.
## Program
```
def rail_fence_encrypt(text, rails):
    fence = [['\n' for _ in range(len(text))]
             for _ in range(rails)]
             
    row = 0
    direction = 1
    
    for col, char in enumerate(text):
        fence[row][col] = char
        
        if row == 0:
            direction = 1
        elif row == rails - 1:
            direction = -1
            
        row += direction
        
    encrypted_text = ""
    
    for row in fence:
        for char in row:
            if char != '\n':
                encrypted_text += char
                
    return encrypted_text

message = input("Enter the plaintext: ")
rails = int(input("Enter the number of rails: "))

ciphertext = rail_fence_encrypt(message, rails)

print("Plaintext:", message)
print("Encrypted text:", ciphertext)
```
## output
<img width="1917" height="975" alt="image" src="https://github.com/user-attachments/assets/71b60d9f-8f84-4643-bcc5-ac95794f9ef2" />


## Result
The program executed successfully


