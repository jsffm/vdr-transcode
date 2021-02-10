# vdr-transcode
Transcode
VDR Aufnahme mit ffmpeg in h264 oder hevc umwandeln. Der Script ist dafür 
gedacht, einzelne oder mehrere Aufnahmen so nach h264 zu wandeln, dass sie 
kompatibel zum vdr bleiben. Platzersparnis: bei Aufzeichnungen von ÖRs mit 
großen Bitraten Faktor 3 und mehr (mpeg2 -> h264). 

Export und Import möglich. 

Bearbeitung von Video-Dateien ist ebenfalls möglich.

Aufgerufen wird der Script auf der cli im Aufnahmeverzeichnis der jeweiligen 
Aufnahme, genauer gesagt im .rec Verzeichnis. Sollen eine größere Menge von 
Aufnahmen gewandelt werden siehe Automation.

Eine vdr-Aufzeichnung nach mp4 exportieren: (Standard-Eingabe ist vdr)

vt -o mp4

Ein mp4 oder mkv nach vdr konvertieren: (Standard-Ausgabe ist vdr)

vt -i &lt;datei>

Aufzeichnung in mpeg2 nach h264 konvertieren um Platz zu sparen 
(mpeg2 -> h264 ist Standard)

vt kein Parameter notwendig.

Aufzeichnung nach hevc konvertieren um Platz zu sparen, derzeit nur mit 
NVIDIA-Karte mit encoder oder vaapi möglich, per CPU sehr zeitaufwändig. 
Sinnvoll bei HD.

vt -h264 hevc

Standard Vorgaben können in einer Datei /etc/vdr-transcode.conf eingetragen 
werden.

## Automation:

Aufzeichnungen werden durch eine Datei vt.conf gekennzeichnet, dort können 
Parameter zur Bearbeitung enthalten sein. Parameter können mit vt --conf 
angelegt werden.

Der Prozess wird mit vt --as & gestartet und kann mit vt --ak beendet werden.

Suchpfade werden in /etc/vdr-transcode-s.conf angelegt.
