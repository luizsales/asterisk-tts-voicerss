### Asterisk com TTS

Exemplo de utilização com ISSABEL-PBX : http://voicerss.org

Execute o procedimento abaixo:
 
```
cd /usr/src
git clone https://github.com/luizsales/asterisk-tts-voicerss.git
cd asterisk-tts-voicerss
chown asterisk.asterisk voicerss_tts.php 
chmo 755 voicerss_tts.php 

```


Para executar esse exemplo, adicione as linhas abaixo no contexto desejado:

```
exten => 1234,1,Answer()
exten => 1234,n,Set(voicercode=pt-br)
exten => 1234,n,Set(translated=Ola, Luiz Sales, boa noite!)
exten => 1234,n,system(/usr/src/asterisk-tts-voicerss/voicerss_tts.php "${translated}" ${voicercode} "/tmp/${UNIQUEID}")
exten => 1234,n,Wait(3)
exten => 1234,n,Playback(/tmp/${UNIQUEID})  
```


