<h1>Ceaser Cipher Python Script</h1>

import string
<br />

alphabets = string.ascii_lowercase + string.ascii_lowercase
<br />

sentence = list(input('Enter your text: \n').lower())
<br />

what_to_do = input('Enter encrypt to ENCRYPT, decrypt to DECRYPT, exit \
    to EXIT the program \n').lower()
<br />

shift_number = int(input('Enter your shift number from 1 to 25: \n'))
<br />

end_program = False
<br />

while not end_program:
<br />
    # search through the enter text
<br />
    if what_to_do == 'encrypt':
<br />
        for i in range(len(sentence)):
<br />
            # get position of each character within the sentence
<br />
            if sentence[i] == ' ':
<br />
                sentence[i] = ' '
<br />
            else:
<br />
                new_letter = alphabets.index(sentence[i]) + shift_number
<br />
                sentence[i] = alphabets[new_letter]
<br />
        # convert the list back to a string
<br />
        print(''.join(map(str, sentence)))
<br />
        end_program = True
<br />
    elif what_to_do == 'decrypt':
<br />
        for i in range(len(sentence)):
<br />
            if sentence[i] == ' ':
<br />
                sentence[i] = ' '
<br />
            else:
<br />
                new_letter = alphabets.index(sentence[i]) - shift_number
<br />
                sentence[i] = alphabets[new_letter]
<br />
        # convert the list back to a string
<br />
        print(''.join(map(str, sentence)))
<br />
        end_program = True
<br />
    else:
<br />
        decide = input(
<br />
            'Invalid entry, try again Y for YES, N for NO: \n').lower()
<br />
        if decide == 'y':
<br />
            sentence = list(input('Enter your yext: \n').lower())
<br />
            what_to_do = input('Enter encrypt to ENCRYPT, decrypt to DECRYPT, exit \
<br />
                to EXIT the program \n').lower()
<br />
            shift_number = int(
<br />
                input('Enter your shift number from 1 to 25: \n'))
<br />
        else:
<br />
            end_program = True
<br />
