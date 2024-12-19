mport ipaddress

def ip_info(ip):
    try:
        # Создаем объект IP-адреса
        ip_obj = ipaddress.ip_address(ip)
        
        # Выводим информацию об IP-адресе
        print(f"IP-адрес: {ip_obj}")
        print(f"Версия: {ip_obj.version}")
        print(f"Частный: {ip_obj.is_private}")
        print(f"Мультитрансляция: {ip_obj.is_multicast}")
        print(f"Циклический: {ip_obj.is_loopback}")
        print(f"Неопределенный: {ip_obj.is_unspecified}")
        print(f"Префикс сети (если есть): {ip_obj.network if ip_obj.version == 6 else 'Не применимо для IPv4'}")
    except ValueError:
        print(f"Неверный IP-адрес: {ip}")

# Пример использования
ip = "192.168.1.1"
ip_info(ip)

ip = "2001:0db8:85a3:0000:0000:8a2e:0370:7334"
ip_info(ip)
