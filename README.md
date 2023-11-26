MORSE_CODE_DICT = { 'A':'.-',
                    'B':'-...',
                    'C':'-.-.',
                    'D':'-..',
                    'E':'.',
                    'F':'..-.', 'G':'--.', 'H':'....',
                    'I':'..', 'J':'.---', 'K':'-.-',
                    'L':'.-..', 'M':'--', 'N':'-.',
                    'O':'---', 'P':'.--.', 'Q':'--.-',
                    'R':'.-.', 'S':'...', 'T':'-',
                    'U':'..-', 'V':'...-', 'W':'.--',
                    'X':'-..-', 'Y':'-.--', 'Z':'--..',
                    '1':'.----', '2':'..---', '3':'...--',
                    '4':'....-', '5':'.....', '6':'-....',
                    '7':'--...', '8':'---..', '9':'----.',
                    '0':'-----', ', ':'--..--', '.':'.-.-.-',
                    '?':'..--..', '/':'-..-.', '-':'-....-',
                    '(':'-.--.', ')':'-.--.-'}

DECRYPT_CODE_DICT = {value : key for key , value in MORSE_CODE_DICT.items()}



def encrypt(messge):
    encrypt_message = ""
    for char in messge:
        if  char.upper() in MORSE_CODE_DICT:
          encrypt_message += MORSE_CODE_DICT[char.upper()] +" "

    return encrypt_message


def decrypt(messge):
    decrypt_message = ""
    for char in messge.split():

          decrypt_message += DECRYPT_CODE_DICT[char]

    return decrypt_message


convert = True
while convert:

    trigger = input("input '1' for encrypt, '2' for decrypt, 'exit' to EXIT  :")

    if trigger == "1":
        message = input("text to be encrypt :")
        print(encrypt(message))

    elif trigger == "2":
        message = input("text to be decrypt:")
        print(decrypt(message))

    elif trigger == "exit":

        convert = False
