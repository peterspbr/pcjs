---
layout: page
title: "PC-SIG Diskette Library (Disk #346)"
permalink: /software/pcx86/sw/misc/pcsig/0001-0999/DISK0346/
machines:
  - id: ibm5160
    type: pcx86
    config: /machines/pcx86/ibm/5160/cga/256kb/machine.xml
    diskettes: /machines/pcx86/diskettes.json,/disks/pcsigdisks/pcx86/diskettes.json
    autoGen: true
    autoMount:
      B: "PC-SIG Library Disk #0346"
    autoType: $date\r$time\rB:\rDIR\r
---

{% include machine.html id="ibm5160" %}

{% comment %}info_begin{% endcomment %}

## Information about "YOUR ART"

    How to Start: Type: MENU (press enter).
    
    Suggested Registration: $100.00 for full user registration.
    
    File Descriptions:
    
    AUTOEXEC BAT  Start Up.
    KD-DRAW  EXE  Main drawing program.
    KD-DRAW  TXT  Program text.
    KD-DRAW  HLP  Help file for program.
    KD-PAINT PIC  Paint colors.
    KD-PTRN  PIC  64 fill patterns.
    KD-FONT? FNT  Text font files.
    KD-MOUSE MSC  Mouse files.
    KD-MOUSE COM  Mouse files.
    KD-MSMOS DEF  Mouse files.
    KD-MSMOS MNU  Mouse files.
    KD-PRNT? TBL  Printer tables.
    KD-UPDAT TXT  Update information.
    KD-MENU  TXT  DOS Menu.
    KD-DRAW  HOT  Hot Key definition file.
    BASRUN   EXE  Used by other EXE files.
    DATEIT   EXE  Replaces DOS DATE.
    CAMERA   COM  Screen capture.
    KD-TRANS EXE  Macro to text translation.
    KEYTBL   DAT  Translation table used by KD-TRANS.EXE.
    H        BAT  DOS help info.
    I        BAT  Copyright info.
    KD       BAT  Runs KD-DRAW.
    DEMO     BAT  Sample Macro file demo.
    SLIDEMO  BAT  Runs SCNSHOW.MCR on library disk.
    DOC      BAT  Prints Documentation.
    INSTALL  BAT  Copies disk or installs to hard disk.
    MENU     BAT  ---!!!!RUN THIS FIRST!!!!---
    H        BAT  DOS help info.
    I        BAT  Copyright info.
    KD       BAT  Runs KD-DRAW.
    DEMO     BAT  Sample Macro file demo.
    SLIDEMO  BAT  Runs SCNSHOW.MCR on library disk.
    DOC      BAT  Prints Documentation.
    INSTALL  BAT  Copies disk or installs to hard disk.
    MENU     BAT  ---!!!!RUN THIS FIRST!!!!---
    XTSUNIT  PTN  Part of YOUART
    YA1V4    EXE  Program to generate medium res graphics
    YA1V4    DOC  Documentation for YA1V4
{% comment %}info_end{% endcomment %}

{% comment %}samples_begin{% endcomment %}

## YA1LOOK.BAS

```bas
10 GOTO 60
20 ' YA1LOOK.BAS   YOURART1 PICTURE DISPLAY PROGRAM
30 ' JULY 1984     EVERETT DELANO
40 '               P.O. BOX 205
50 '               ELK CITY, OKLA. 73648
60 DEF SEG=0:IF (PEEK(&H410) AND &H30) <> &H30 THEN 70 ELSE 1360
70 DEF SEG:POKE 106,0
80 SCREEN 0,1,0,0:WIDTH 80:KEY OFF
90 DEFINT A-Z:DIM SORT$(101)
100 ON ERROR GOTO 1170
110 GOSUB 1390
120 FOR COUNT=1 TO 10:KEY COUNT,"":NEXT
130 COLOR 7,4,1:CLS
140 LEGEND$="* Press   Esc   To EXIT *"
150 LOCATE 25,28:COLOR 2:PRINT LEGEND$;:COLOR 7
160 TITLE$="* * * * YOURART  MEDIUM  RESOLUTION  DISPLAY * * * *"
170 CENTER=(80-LEN(TITLE$))/2
180 LOCATE 1,CENTER,0:PRINT TITLE$
190 LOCATE 2,22:COLOR 19:PRINT "(MAXIMUM OF 88 PICTURES PER SESSION)":COLOR 7
200 LOCATE 5,8,0
210 PRINT"WHICH DRIVE CONTAINS THE PICTURES: ";
220 INK$=INKEY$:IF LEN(INK$)<>1 THEN  220
230 IF INK$=CHR$(27) THEN 1230
240 PRINT INK$;
250 IF ASC(INK$)>96 AND ASC(INK$)<103 THEN INK$=CHR$(ASC(INK$)-32)
260 IF INSTR("ABCDEF",INK$)<1 THEN LOCATE 6,1,0:GOSUB 1120:GOTO 200
270 DRIVE$=LEFT$(INK$,1)+":"
280 LOCATE 7,8,0
290 PRINT "MANUAL OR AUTOMATIC DISPLAY"
300 LOCATE 8,27,0:PRINT "SELECT M or A : ";
310 INK$=INKEY$:IF INK$="" THEN 310
320 IF INK$=CHR$(27) THEN 1230
330 PRINT INK$;
340 S=INSTR("MmAa",INK$):IF S<1 THEN LOCATE 9,1,0:GOSUB 1120:GOTO 300
350 IF S=1 OR S=2 THEN GOTO 790
360 LOCATE 25,26:BEEP:COLOR 18:PRINT "* Enter    QUIT    To EXIT *";:COLOR 7
370 LOCATE 10,8,0
380 PRINT "DISPLAY DURATION IN SECONDS"
390 LOCATE 11,1,0:PRINT STRING$(79," ");:LOCATE 11,29,0
400 INPUT "MAXIMUM  60 : ",SECS$
410 IF SECS$="QUIT" OR SECS$="quit" OR SECS$="Quit" THEN 1230
420 SECS=VAL(SECS$)
430 IF SECS>60 THEN LOCATE 11,1,0:GOSUB 1120:GOTO 390
440 LOCATE 5,8,0
450 IF S=1 OR S=2 THEN GOTO 790
460 WIDTH 80:COLOR 0,0,0:CLS
470 FILES DRIVE$+"*.PIC"
480 GOSUB 1260
490 CROW=CSRLIN
500 COUNT=0
510 LOCATE 1,1,1
520 FOR ROW=STL TO CROW
530 FOR COL=1 TO 72 STEP STP
540 COUNT=COUNT+1
550 FOR N=0 TO 11
560 SORT$(COUNT)=SORT$(COUNT)+CHR$(SCREEN(ROW,(COL+N)))
570 NEXT N
580 IF LEFT$(SORT$(COUNT),1)=" " THEN COUNT=COUNT-1 :GOTO 620
590 SORT$(COUNT)=DRIVE$+SORT$(COUNT)
600 NEXT COL
610 NEXT ROW
620 IF COUNT>88 THEN 1240
630 TOTPICS=COUNT
640 FOR COUNT=1 TO TOTPICS-1
650 FOR PLACE=COUNT+1 TO TOTPICS
660 IF SORT$(PLACE)<SORT$(COUNT) THEN SWAP SORT$(COUNT),SORT$(PLACE)
670 NEXT PLACE
680 NEXT COUNT
690 SCREEN 1,0:COLOR 0,0
700 FOR PIC=1 TO TOTPICS
710 BLOAD SORT$(PIC)
720 GOSUB 760
730 CLS
740 NEXT PIC
750 GOTO 1230
760 IF VMODE$="M" THEN GOTO 910
770 FOR CLOCK!=1 TO 1100*SECS:NEXT
780 RETURN
790 CLS:LOCATE 5,22,0:PRINT "Grey Plus Key `+' for next picture."
800 LOCATE 7,22,0:PRINT "Grey Minus Key `-' for previous picture."
810 LOCATE 9,22,0:PRINT "F1 thru F8 Change Background Color"
820 LOCATE 11,22,0:PRINT "F9 and F10 Change Pallette"
830 LOCATE 13,22,0:PRINT "Esc  Key to EXIT from display"
840 LOCATE 19,22,0:PRINT "Press   ";CHR$(17);CHR$(196);CHR$(217);"   to begin"
850 LOCATE 25,26,0:COLOR 18:PRINT "* Press   Esc   To Exit *";:COLOR 7
860 INK$=INKEY$:IF INK$="" THEN 860
870 IF INK$=CHR$(27) THEN 1230
880 IF INK$<>CHR$(13) THEN 860
890 VMODE$="M"
900 GOTO 460
910 INK$=INKEY$:IF INK$="" THEN 910 ELSE IF LEN(INK$)>1 THEN 960
920 IF INK$="+" THEN RETURN
930 IF INK$="-" THEN PIC=PIC-2:GOSUB 1100:RETURN
940 IF INK$=CHR$(27) THEN 1230
950 GOTO 910
960 IF LEN(INK$)=2 THEN 970 ELSE 910
970 S=ASC(MID$(INK$,2,1))-58:IF S<1 OR S>10 THEN 910
980 ON S GOSUB 1000,1010,1020,1030,1040,1050,1060,1070,1080,1090
990 GOTO 910
1000 COLOR 0:RETURN
1010 COLOR 1:RETURN
1020 COLOR 2:RETURN
1030 COLOR 3:RETURN
1040 COLOR 4:RETURN
1050 COLOR 5:RETURN
1060 COLOR 6:RETURN
1070 COLOR 7:RETURN
1080 COLOR ,0:RETURN
1090 COLOR ,1:RETURN
1100 IF PIC=-1 THEN PIC=0
1110 RETURN
1120 BEEP:LOCATE CSRLIN,20,0:PRINT "IMPROPER RESPONSE - PLEASE TRY AGAIN!!";
1130 FOR COUNT=1 TO 5000:NEXT
1140 LOCATE CSRLIN,1,0:PRINT STRING$(79," ");
1150 LOCATE CSRLIN-1,1,0:PRINT STRING$(79," ");
1160 BEEP:RETURN
1170 IF ERL<>470 THEN 1200
1180 COLOR 14,1,0:CLS:LOCATE 12,10,1:PRINT "NO PICTURE FILES FOUND"
1190 GOSUB 1500:END
1200 SCREEN 0,1,0,0:WIDTH 80:COLOR 14,1,0:CLS
1210 LOCATE 12,10,11:PRINT "ERROR";ERR;" OCCURED IN LINE";ERL
1220 GOSUB 1500:END
1230 SCREEN 0,1,0,0:WIDTH 80:COLOR 14,1,0:CLS:GOSUB 1500:END
1240 COLOR 14,1,0:CLS:LOCATE 12,10,1:PRINT "TOO MANY PICTURE FILES!!"
1250 GOSUB 1500:END
1260 IF SCREEN(1,14) = 32 THEN 1290
1270 STP=13
1280 GOTO 1330
1290 IF SCREEN(2,14) = 32 THEN 1320
1300 STP=13
1310 GOTO 1330
1320 STP=18
1330 IF SCREEN(1,9) = 46 THEN STL=1:GOTO 1350
1340 STL=2
1350 RETURN
1360 DEF SEG:POKE 106,0:COLOR 14,1,0:CLS:BEEP
1370 LOCATE 12,15:PRINT "PROGRAM REQUIRES IBM COMPATABLE COLOR GRAPHICS CARD!"
1380 BEEP:END
1390 DEF SEG:P=0
1400 FOR COUNT=1 TO 10
1410 KEYHOLD$(COUNT)=""
1420 WHILE PEEK(P+1619)<>0
1430 KEYHOLD$(COUNT)=KEYHOLD$(COUNT)+CHR$(PEEK(P+1619))
1440 P=P+1
1450 WEND
1460 P=COUNT*16
1470 KEYHOLD$(COUNT)=KEYHOLD$(COUNT)+CHR$(0)
1480 NEXT
1490 RETURN
1500 DEF SEG
1510 FOR COUNT=1 TO 10
1520 FOR PLACE=1 TO LEN(KEYHOLD$(COUNT))
1530 POKE 1618+(COUNT-1)*16+PLACE,ASC(MID$(KEYHOLD$(COUNT),PLACE))
1540 NEXT PLACE,COUNT
1550 KEY OFF:KEY ON
1560 RETURN
```

{% comment %}samples_end{% endcomment %}

### Directory of PC-SIG Library Disk #0346

     Volume in drive A has no label
     Directory of A:\

    YA1V4    EXE     62423   9-20-84   8:56a
    YA1V4    DOC     54993   9-20-84  11:17p
    README   BAT       768   9-20-84   8:56a
    CHSHEET  DOC      1762   9-20-84   8:56a
    YA1-1    HLP      1280   9-20-84   8:56a
    YA1-2    HLP      1280   9-20-84   8:56a
    YA1-3    HLP      1280   9-20-84   8:56a
    YA1-4    HLP      1408   9-20-84   8:56a
    YA1-5    HLP      1152   9-20-84   8:56a
    YA1-6    HLP      1152   9-20-84   8:56a
    YA1-7    HLP      1152   9-20-84   8:56a
    YA1-8    HLP       939   9-20-84   8:56a
    YA1F-1   FNT      1145   9-20-84   8:56a
    YA1F-2   FNT      1146   9-20-84   8:56a
    YA1F-3   FNT      1145   9-20-84   8:56a
    YA1F-4   FNT      1685   9-20-84   8:56a
    YA1F-5   FNT      3810   9-20-84   8:56a
    YA1F-6   FNT      5939   9-20-84   8:56a
    YA1F-7   FNT     11381   9-20-84   8:56a
    YA1F-8   FNT      9369   9-20-84   8:56a
    YA1LOOK  BAS      4096   8-28-84   4:03p
    TIMEUS   COM       658  10-24-83  12:20p
    GO       BAT       875   1-05-87   1:09p
    PCSUNIT  PTN      8064  11-26-66
    XTSUNIT  PTN      8064   3-03-85  12:20p
    MONITOR  PTN      8064  10-26-64
    KEYBOARD PTN      8064   3-03-85  12:20p
    FILES346 TXT      1567   1-05-87   1:02p
    DEFAULT  PIC      6144  10-22-86   1:52p
           29 file(s)     210805 bytes
                           98304 bytes free