import requests
import random
import os


TEMP_FOLDER = 'temp'
FIRST_NAMES_FILE = os.path.join(TEMP_FOLDER, 'Temp1.txt')
LAST_NAMES_FILE = os.path.join(TEMP_FOLDER, 'Temp2.txt')
PASS_MESSAGES_FILE = os.path.join(TEMP_FOLDER, 'Temp3.txt')
VERSION = "1.4.5"

FIRST_NAMES_URL = 'https://raw.githubusercontent.com/myalt2335/Dictionary/main/names/CommonFirstNames.txt'
LAST_NAMES_URL = 'https://raw.githubusercontent.com/myalt2335/Dictionary/main/names/CommonLastNames.txt'
PASS_MESSAGES_URL = 'https://raw.githubusercontent.com/myalt2335/Dictionary/main/misc/Passmessagesforgame.txt'

def ensure_temp_folder():
    os.makedirs(TEMP_FOLDER, exist_ok=True)

def fetch_data(url, filename):
    if os.path.exists(filename):
        with open(filename, 'r') as file:
            return file.read().splitlines()

    try:
        response = requests.get(url)
        response.raise_for_status()
        data = response.text.splitlines()
        with open(filename, 'w') as file:
            file.write('\n'.join(data))
        return data
    except requests.RequestException as e:
        print(f"Failed to fetch data from {url}: {e}")
        return []

def cleanup_temp_files():
    for filename in [FIRST_NAMES_FILE, LAST_NAMES_FILE, PASS_MESSAGES_FILE]:
        try:
            os.remove(filename)
        except FileNotFoundError:
            pass
    try:
        os.rmdir(TEMP_FOLDER)
    except OSError:
        pass

def generate_character(first_names, last_names):
    return {
        "name": f"{random.choice(first_names)} {random.choice(last_names)}",
        "age": random.randint(1, 80)
    }

def get_user_input(prompt, valid_responses):
    while True:
        response = input(prompt).strip().upper()
        if response in valid_responses:
            return response
        print(f"Invalid input. Please enter one of {valid_responses}.")

def start_game_loop(first_names, last_names, pass_messages):
    while True:
        start = get_user_input("Start? (Y/N): ", {'Y', 'N'})
        if start != 'Y':
            print("Exiting game.")
            break

        while True:
            character = generate_character(first_names, last_names)
            print(f"{character['name']}, {character['age']}")

            decision = get_user_input("Do you want to date? (Y/N): ", {'Y', 'N'})
            if decision == 'Y':
                if character['age'] > 17:
                    print("You lose! Drake would never do that.")
                    break
                else:
                    print("You win! Drake would approve.")
            else:
                if character['age'] <= 17:
                    print("You lose! Drake would date them.")
                    break
                else:
                    print(random.choice(pass_messages))

        play_again = get_user_input("Do you want to start over? (Y/N): ", {'Y', 'N'})
        if play_again != 'Y':
            print("Exiting game.")
            break

def main():
    ensure_temp_folder()

    first_names = fetch_data(FIRST_NAMES_URL, FIRST_NAMES_FILE)
    last_names = fetch_data(LAST_NAMES_URL, LAST_NAMES_FILE)
    pass_messages = fetch_data(PASS_MESSAGES_URL, PASS_MESSAGES_FILE)

    if not first_names or not last_names or not pass_messages:
        print("Could not fetch necessary data. Exiting.")
        cleanup_temp_files()
        return

    print(f"Drake Dating Sim - Version {VERSION}")

    try:
        start_game_loop(first_names, last_names, pass_messages)
    except KeyboardInterrupt:
        print("\nExiting game due to user interruption.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")
    finally:
        cleanup_temp_files()

if __name__ == "__main__":
    main()
