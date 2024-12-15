.section .data
    hello_msg:     .asciz "👋 Hi, I’m Jettthuurooww 😎\n"
    interests_msg: .asciz "👀 I’m interested in computer vision (👁️🤖👁️) and LLMs (🤖🙊)\n"
    learning_msg:  .asciz "🌱 I’m currently learning computer vision (👁️🤖👁️) and LLMs (🤖🙊)\n"
    collab_msg:    .asciz "💞️ I’m looking to collaborate with my self.\n"
    pronouns_msg:  .asciz "😄 Pronouns: he/him/apache helicopter\n"
    funfact_msg:   .asciz "⚡ Fun fact: I can still be productive even with 2 nights of no sleep (*sips coffee*).\n"

.section .text
    .global _start

_start:
    ldr x0, =hello_msg         
    bl print_string            

    ldr x0, =interests_msg     
    bl print_string            

    ldr x0, =learning_msg      
    bl print_string            

    ldr x0, =collab_msg        
    bl print_string    
    
    ldr x0, =pronouns_msg     
    bl print_string            

    ldr x0, =funfact_msg       
    bl print_string            

    b exit_program             // ext

print_string:
    mov x1, x0               
    mov x2, #0              

count_chars:
    ldrb w3, [x1, x2]         
    cbz w3, write_string     
    add x2, x2, #1           
    b count_chars             

write_string:
    mov x8, #64               
    mov x0, #1                
    svc #0                    
    ret

exit_program:
    mov x8, #93               
    mov x0, #0                
    svc #0                   

<!---
JbSante/JbSante is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
