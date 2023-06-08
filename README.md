# Hello I am Noutz!
___________________________________________________________________________________________________________________________________________

# Youtube
[![YouTube](https://i.im.ge/2023/06/08/hBSCFJ.1384060.png)](https://www.youtube.com/@NoutzChill/)

``` print("Hello World")```

# Biography
___________________________________________________________________________________________________________________________________________
I'm from Brazil and my favorite programming language is Python. I work mainly with project development using this amazing language. I'm currently using Visual Studio Code as my main code editor.

I have experience in several interesting projects, such as the implementation and use of the Nmap library, which is a powerful network mapping tool. In addition, I have been exploring other areas of development such as data analysis, web scraping and task automation.

Welcome to explore my projects here on GitHub. Please feel free to contact me if you have any questions or suggestions. Let's collaborate and learn together!

Thanks for the visit!

# Code ![Python](https://i.im.ge/2023/06/08/hBUrqz.5848152fcef1014c0b5e4967.png)
_________________________________________________________________________________________________________________________________________

```python
import socket
from concurrent.futures import ThreadPoolExecutor, as_completed
from urllib.parse import urlparse

NUM_THREADS = 50

target_url = input('㊦ | Введите целевой IP/САЙТ/Digite o IP/SITE alvo: ')
parsed_url = urlparse(target_url)
target_host = parsed_url.netloc.split(':')[0]  # Extrai o nome do host da URL
port_range = range(1, 8080)  # Esta faixa de porta pode ser alterada pelo usuário

def scan_port(port):
    sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    sock.settimeout(0.5)
    result = sock.connect_ex((target_host, port))
    sock.close()
    return port, result == 0

open_ports = []

with ThreadPoolExecutor(max_workers=NUM_THREADS) as executor:
    futures = [executor.submit(scan_port, port) for port in port_range]
    num_scanned = 0
    for future in as_completed(futures):
        num_scanned += 1
        port, is_open = future.result()
        if is_open:
            open_ports.append(port)
        print(f"\rпорт сканирования/Escaneando porta {port} de {len(port_range)}", end="")

print("\nPortas abertas:")
for port in open_ports:
    print(port)

input('Нажмите Enter, чтобы выйти. Сделано Noutz/Aperte enter para sair Feito por Noutz . ')
```

# Other Redes
http://bit.ly/3HAmTFc

