### Asterisk com TTS

Exemplo de utilização com ISSABEL-PBX : [http://voicerss.org/][PlDb]

Para executar esse exemplo, adicione as linhas abaixo no 

```
exten => 1234,1,Answer()
exten => 1234,n,Set(voicercode=pt-br)
exten => 1234,n,Set(translated=Ola, Luiz Sales, boa noite!)
exten => 1234,n,system(/usr/src/voicerss/voicerss_tts.php "${translated}" ${voicercode} "/tmp/${UNIQUEID}")
exten => 1234,n,Wait(3)
exten => 1234,n,Playback(/tmp/${UNIQUEID})  
```

