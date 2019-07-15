- Gestartet wird ein Simulationslauf durch starten von izamod.py
- Einstellungen f�r den Lauf (Datenbasis, Reformen, Setzen von Schalten) werden in settings.py gemacht.
- Die Datenbasis ist zwecks einfacherer Nachverfolgung von Erwerbshistorien etc. das SOEP-Long. 
- Reformen (z.b. 'GRUNDEK') werden in settings spezifiziert und per if-Bedingung in taxtransfer.py geschaltet.

- Bemerkungen zur Datenaufbereitung:
	- Die SOEP-Haushalte werden in tax_units aufgeteilt, die immer entweder einen oder zwei Erwachsene haben.
	Beispiel: Ein Paar mit drei Kindern im Alter von 25, 17 und 14 Jahren. Dazu noch die Gro�mutter. Dann ist das Paar mit den beiden j�ngeren Kindern eine tax_unit, das erwachsene Kind eine zweite, und die Oma die dritte tax_unit. Diese Aufteilung funktioniert (noch) nicht in allen F�llen. Die wenigen F�lle, in denen es nicht funktioniert, werden gel�scht.
	
Dementsprechend muss man darauf achten, ob man die z.B. die Anzahl der Kinder im SOEP-Haushalt ('child_num') oder in der Tax Unit abfragt ('child_num_tu')

- Die Steuer-Transfer-Parameter seit 1984 (Steuertarife, Transferh�hen etc.) liegen in /data/params/params.xlsx . Dort steht auch die entsprechende Gesetzesgrundlage. In taxtransfer.py werden die Parameter f�r das entsprechende Jahr in das dictionary 'tb' geladen.
 

- Das Steuer-Transfersystem ist noch nicht f�r fr�here Jahre (z.b. vor Hartz IV) implementiert. 