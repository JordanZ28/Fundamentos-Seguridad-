
# Objetivo 

This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java)
# Solución 
```
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Revers/Parte1/Vaul1]
└─$ cat VaultDoor1.java       
import java.util.*;

class VaultDoor1 {
    public static void main(String args[]) {
        VaultDoor1 vaultDoor = new VaultDoor1();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // I came up with a more secure way to check the password without putting
    // the password itself in the source code. I think this is going to be
    // UNHACKABLE!! I hope Dr. Evil agrees...
    //
    // -Minion #8728
    public boolean checkPassword(String password) {
        return password.length() == 32 &&
               password.charAt(0)  == 'd' &&
               password.charAt(29) == 'a' &&
               password.charAt(4)  == 'r' &&
               password.charAt(2)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(3)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(1)  == '3' &&
               password.charAt(7)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(5)  == '4' &&
               password.charAt(9)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(8)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(6)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == '6' &&
               password.charAt(30) == 'f' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == 'd' &&
               password.charAt(26) == 'f' &&
               password.charAt(31) == '4';
    }
}
                                                                                                                                           
┌──(jordan㉿kali)-[~/Pico/Revers/Parte1/Vaul1]
└─$ nano v1
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Revers/Parte1/Vaul1]
└─$ cat v1             
               password.charAt(00)  == 'd' &&
               password.charAt(29) == 'a' &&
               password.charAt(04)  == 'r' &&
               password.charAt(02)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(03)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(01)  == '3' &&
               password.charAt(07)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(05)  == '4' &&
               password.charAt(09)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(08)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(06)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == '6' &&
               password.charAt(30) == 'f' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == 'd' &&
               password.charAt(26) == 'f' &&
               password.charAt(31) == '4'

                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Revers/Parte1/Vaul1]
└─$ cat v1 | sort

               password.charAt(00)  == 'd' &&
               password.charAt(01)  == '3' &&
               password.charAt(02)  == '5' &&
               password.charAt(03)  == 'c' &&
               password.charAt(04)  == 'r' &&
               password.charAt(05)  == '4' &&
               password.charAt(06)  == 'm' &&
               password.charAt(07)  == 'b' &&
               password.charAt(08)  == 'l' &&
               password.charAt(09)  == '3' &&
               password.charAt(10) == '_' &&
               password.charAt(11) == 't' &&
               password.charAt(12) == 'H' &&
               password.charAt(13) == '3' &&
               password.charAt(14) == '_' &&
               password.charAt(15) == 'c' &&
               password.charAt(16) == 'H' &&
               password.charAt(17) == '4' &&
               password.charAt(18) == 'r' &&
               password.charAt(19) == '4' &&
               password.charAt(20) == 'c' &&
               password.charAt(21) == 'T' &&
               password.charAt(22) == '3' &&
               password.charAt(23) == 'r' &&
               password.charAt(24) == '5' &&
               password.charAt(25) == '_' &&
               password.charAt(26) == 'f' &&
               password.charAt(27) == '6' &&
               password.charAt(28) == 'd' &&
               password.charAt(29) == 'a' &&
               password.charAt(30) == 'f' &&
               password.charAt(31) == '4'
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Revers/Parte1/Vaul1]
└─$ cat v1 | sort | awk '{printf($3)'
awk: cmd. line:1: {printf($3)
awk: cmd. line:1:            ^ unexpected newline or end of string
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Revers/Parte1/Vaul1]
└─$ cat v1 | sort | awk '{print($3)' 
awk: cmd. line:1: {print($3)
awk: cmd. line:1:           ^ unexpected newline or end of string
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Revers/Parte1/Vaul1]
└─$ cat v1 | sort | awk '{print($3)]'
awk: cmd. line:1: {print($3)]
awk: cmd. line:1:           ^ syntax error
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Revers/Parte1/Vaul1]
└─$ cat v1 | sort | awk '{print($3)}'

'd'
'3'
'5'
'c'
'r'
'4'
'm'
'b'
'l'
'3'
'_'
't'
'H'
'3'
'_'
'c'
'H'
'4'
'r'
'4'
'c'
'T'
'3'
'r'
'5'
'_'
'f'
'6'
'd'
'a'
'f'
'4'
                                                                                                                                                                                                       
┌──(jordan㉿kali)-[~/Pico/Revers/Parte1/Vaul1]
└─$ cat v1 | sort | awk '{print($3)}' | tr -d '''' | tr -d '\n'








'd''3''5''c''r''4''m''b''l''3''_''t''H''3''_''c''H''4''r''4''c''T''3''r''5''_''f''6''d''a''f''4'                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Revers/Parte1/Vaul1]
└─$ cat v1 | sort | awk '{print($3)}' | tr -d "'" | tr -d '\n' 

d35cr4mbl3_tH3_cH4r4cT3r5_f6daf4                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Revers/Parte1/Vaul1]
└─$ 
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Revers/Parte1/Vaul1]
└─$ javac VaultDoor1.java       
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Revers/Parte1/Vaul1]
└─$ java VaultDoor1       
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_f6daf4}
Access granted.
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Revers/Parte1/Vaul1]
└─$ 
                                                                                                                             
┌──(jordan㉿kali)-[~/Pico/Revers/Parte1/Vaul1]
└─$ 

```
# Notas 

