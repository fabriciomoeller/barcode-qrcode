# barcode-qrcode

## Uso de certificado ssl

1. Primeiro, instale o OpenSSL se ainda não estiver instalado:
´´´ bash
sudo apt update
sudo apt install openssl
´´´
2. Gere um certificado autoassinado (como mencionado anteriormente):
´´´ bash
openssl req -newkey rsa:2048 -new -nodes -x509 -days 3650 -keyout key.pem -out cert.pem
´´´

## servidor http para teste

1.Instale o http-server globalmente via npm:
´´´ bash
npm install -g http-server
´´´
4. Inicie o servidor HTTPS no diretório atual:
´´´ bash
http-server -S -C cert.pem -K key.pem
´´´

Isso iniciará um servidor HTTPS local.

Acesse sua página através de https://localhost:8080 (ou a porta indicada pelo http-server).
Desta forma, você pode testar seu código HTML com o scanner de código de barras em um ambiente HTTPS local, sem necessidade de modificar seu arquivo HTML ou adicionar qualquer script de servidor. É uma solução rápida e eficaz para desenvolvimento e testes locais.
