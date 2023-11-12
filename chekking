import requests
from requests.exceptions import ConnectionError, Timeout

def check_proxy(proxy):
    url = "http://www.google.com"  

    proxies = {
        "http": proxy,
        "https": proxy,
    }

    try:
        response = requests.get(url, proxies=proxies, timeout=10)
        if response.status_code == 200:
            print(f"{proxy} is working.")
            return True
    except (ConnectionError, Timeout):
        print(f"{proxy} is not working.")
        return False

def main(input_file):
    with open(input_file, 'r') as file:
        for line in file:
            proxy = line.strip()
            check_proxy(proxy)

if __name__ == "__main__":
    input_file = input("Enter the path to the input file: ")
    main(input_file)
