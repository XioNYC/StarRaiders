             	;
             		.TITLE 'STAR RAIDERS.	VERSION 25.1	STARDATE-26-JUL-79'
             	;	
             	;	        GAME COMPLETE 17-JUN-79
             	;
             	;	        NOTES
             	;	RAM	0-1FFF
             	;	ROM	A0000-BFFF
             	;	SPILL OVER ROM	 9800-9FFF
             	;	E477G         	   ; PROG START
             	;
             	;	ALPHA CHARACTERS  IN DMA ASCII
             	;
             	;	*CAPS = ASCII EOR $20
             	;	NUMBERS = ASCII
             	;
             	;	40 CHAR = $CC00
             	;	20 CHAR (*CAPS, NUMBERS), = $CC00
             	;	20 CHAR (CAPS, LOWR CASE), = $CE00
             	;
             	;
             	;
             	;	UNIVERSE LOOKS LIKE 	SIGN	HI BYTE		LOW BYTE
             	;	-INFINITY	=	00	00		00
             	;	        0	=	01	00		00
             	;	+INFINITY	=	01	FF		FF
             	;	       -1	=	00	FF		FF
             	;
             	;
             	;
             	;	KEYCODE IS ORED WITH $C0
             	;
             	;
             	;
             	;
             	;
             	;	STRRAM MEMORY DEFINED	STRRAM+		TYPE	NOTES
             	;	             	        	     0		OBJ0	ZYLON
             	;	             	        	     1		OBJ1	ZYLON
             	;	             	        	     2		OBJ2	PHOTON
             	;	             	        	     3		OBJ3	PHOTON
             	;	             	        	     4		MISSILE	PHOTON
             	;	             	        	     5-N	PLAY.	STARS
             	;	             	        	  N+1-M 	PLAY.	EXPLOS STARS
             	;
             	;
             	;
             	;
             		*=$0062
             	;	******************  POWER UP CLEARED RAM  ****************
0062         	MISDIF		; MISSION DIFFICULTY
             		*=*+1
0063         	RESET		; ONE SHOT CONSOL KEY
             		*=*+1
0064         	ATRACT		; GAME OVER FLAF =FF, ATRACT MODE
             		*=*+1
0065         	REPMSG			; REPEAT MESSAGE BYTE
             		*=*+1
0066         	TIMOUT		; ATRACT MODE TIMEOUT REG
             		*=*+1
             	;	*******************************************************
0067         	PAGE0
0067         	PRGOST		; WAIT FOR VBLANK= 00
             		*=*+1
             		**********************  TEMP REG RAM  **********************
0068         	PNTR			; 2 BYTE MISC.  TEMPORARY REG POINTER
             		*=*+2
006A         	TEMP			; TEMPORARY REGISTER
             		*=*+1
006B         	TEMP1			; TEMP REG
             		*=*+1
006C         	TEMP2
             		*=*+1
006D         	TEMP3
             		*=*+1
006E         	TEMP4
             		*=*+1
006F         	NTEMP			; NMI TEMP REQ
             		*=*+1
             	;	*************************************************************
             	;	********************  SHIP SPEED RAM  ***********************
0070         	SPEED			; SPEED O CURISER
             		*=*+1
0071         	WARP			; SPEED DESIRED AS OPPOSED TO SPEED , THE PRESENT SPEED
             		*=*+1
             	;	************************************************************
             	;	*******************  TIMERS RAM  ***************************
0072         	TIMERX		; USED FO STAR INTENSITY
             		*=*+1
0073         	ETIMER			; EXPLOSION TIMEOUT
             		*=*+1
0074         	SECOND			; SECOND TIMEOUT
             		*=*+1
0075         	BSEQTM		; STARBASE SEQUENCER
             		*=*+1
0076         	BINTIM		; BINARY TIMER
             		*=*+1
0077         	BINNMI		; BINARY TIMER IN NMI
             		*=*+1
0078         	JMPTIM		; TIME TO JUMP RAM LOC
             		*=*+1
             	;	************************************************************
             	;	********************  STAR POINTER RAM  ********************
0079         	NSTARS	; LAST BYTE OF STAR RAM TO STORE, EITHER RMLAST OR STLAST
             		*=*+1
007A         	CNSTAR		; LAST BYTE OF STAR RAM TO CLEAR
             		*=*+1
007B         	BASFLG		; STARBASE FLAG
             		*=*+1
007C         	TRKFLG		; AUTOTRACKING = FF
             		*=*+1
007D         	SHENER		; SHIELD ENERGY 0 OR 8
             		*=*+1
007E         	ATENER		; ATTACK COMPUTER ENERGY
             		*=*+1
007F         	ENFLAG		; LS BYTE OF ENERGY , TELLS WHEN TO DEC ENERGY
             		*=*+1
0080         	WPENER			; WARP ENRGY DEPENDS ON WARP
             		*=*+1
             	;	************************************************************
             	;	**************  MISC RAM  **********************************
0081         	SPABAK			; SPACE BACKGROUND COLOR
             		*=*+1
0082         	PHITS			; PHOTON HIT DETECT REGS
             		*=*+2
0084         	PHOFLG		; ONE SHOT PHOTON
             		*=*+1
0085         	PHOTIM			; REPEAT TIMEOUT
             		*=*+1
0086         	LOKLOC			; PHOTON LOCK VECTOR PNTR
             		*=*+1
0087         	PHOTOG			; PHOTON TOGGLE FLAG
             		*=*+1
0088         	LOKWAT		; TIME BEFORE CAN LOCK AGAIN
             		*=*+1
0089         	LOKTAR		; INDEX OF LOCK ON TARGET
             		*=*+1
008A         	HITME		;  SHIP HIT FLAG
             		*=*+1
008B         	REDFKG		; RED ALERT FLAG
             		*=*+1
             	;		**************************************************
             	;	**********************  GALACTIC CHART RAM  ******************
008C         	GVPOS		; CRUISER VPOS ON CHART
             		*=*+1
008D         	GHPOS		; CRUISER HPOS ON CHART
             		*=*+1
008E         	HYVPOS		; CURSOR VPOS ON CHART
             		*=*+1
008F         	HYHPOS		; CURCOR HPOS ON CHART
             		*=*+1
0090         	QUADRT		; QUADRANT STAR RAIDER IS IN
             		*=*+1
0091         	HYPENG		; HYPERWARP ENERGY USED
             		*=*+1
0092         	HYPQAD			; HYPERWARP QUADRANT
             		*=*+1
0093         	KILBAS		; QUAD OF STARBASE, ZYLONS ARE AFTER
             		*=*+1
0094         	KILOCH		; KILL LOC HPOS
             		*=*+1
0095         	KILOCV			; KILL LOC VPOS
             		*=*+1
0096         	JMPPTS			; GRADIENT VALUES
             		*=*+9
009F         	JMPOUT		; JUMP TIMEOUT REG
             		*=*+1
             	;		**************************************************
             	;	*******************  SCREEN MAP DRAWING RAM  ******************
00A0         	HTARGT		; HORIZ TARGET POSIT
             		*=*+1
00A1         	VTARGT			; VERT TARGET POSIT
             		*=*+1
00A2         	TARPTR		; TARGET SEQUENCER
             		*=*+1
00A3         	LOKFLG			; COMPUTER LOCKON
             		*=*+1
00A4         	NUMPTS		; NUMBER OF POINTS TO DRAW
             		*=*+1
00A5         	VDRAW		; VERT POS OF DRAW CURSOR
             		*=*+1
00A6         	HDRAW		; HOR POS OF DRAW CURSOR
             		*=*+1
             	;	*********************************************************
             	;	******************  THINK RAM  **************************
00A7         	ZYTOGG		; WHICH ZYLON
             		*=*+1
00A8         	SEQEN			; SEQUENCER PNTR RAM
             		*=*+2
00AA         	SEQTIM			; SEQUENCER TIMEOUT RAM
             		*=*+2
00AC         	XINDES			; DESIRED XINCRE
             		*=*+2
00AE         	YINDES			; DESIRED YINCRE
             		*=*+2
00B0         	ZINDES			; DESIRED ZINCRE
             		*=*+2
00B2         	XINPRS		;  PRESENT POINTER TO ZYWARP
             		*=*+6
00B8         	BSTRAF		; STRAF BACK 0,OR 1
             		*=*+2
00BA         	ROTTIM		; ROTATION TIMEOUT
             		*=*+4
00BE         	PHEXWT			; PHOTON EXPLOSION WAIT
             		*=*+1
00BF         	ATTARG	; WHICH ZYLON FIRED
             		*=*+1
             	;	************************************************************
             	;	*************************  HYPERWARP RAM  *********************
00C0         	HFLAG		; HYPERWARP ENGAGED FLAG, 00,FF, OR 7F
             		*=*+1
00C1         	HISPED		; HI BYTE SPEED, 0 OR 2=HWARP
             		*=*+1
00C2         	HTIMER			; HWARP TIMER
             		*=*+1
00C3         	HPNTR		; POINTS TO WHICH LINE STARS TO LOAD
             		*=*+1
00C4         	HSTEER		; OLD HWAR CURSOR HPOS
             		*=*+1
00C5         	VSTEER			; OLD HWARP CURSOR VPO
             		*=*+1
00C6         	STERMK			; STEER MASK
             		*=*+1
00C7         	JMPMSK	; INIT TARGETS IN NEW QUAD, MAX DISTANCE FROM SHIP
             		*=*+1
             	;	*************************************************************
             	;	*******************  KEYS, JOYSTICK RAM *********************
00C8         	HORJOY			; 0=NO HORIZ, 01=RIGHT, FF=LEFT
             		*=*+1
00C9         	VERJOY			; 0=NO VERT, 01=DOWN, FF=UP
             		*=*+1
00CA         	THEKEY		; THE KEY IN KBCODE
             		*=*+1
00CB         	RATING		; YOUR RATING
             		*=*+2
00CD         	ENDRAT		; FINAL RATING
             		*=*+1
00CE         	ENDCLS		; FINAL CLASS
             		*=*+1
             	;	*************************************************************
             	;	***************  MESSAGE RAM  ****************************
00CF         	MESTIM			; MESSAGE TIMEOUT
             		*=*+1
00D0         	DISFLG			; DISPLAY TYPE FLAG 0=FRONT,1=BACK,80=GALCHT
             		*=*+1		; 40=SECTOR SCAN
00D1         	SENPTR			; SENTENCE POINTER
             		*=*+1
             	;	*************************************************************
             	;	***************  AUDIO RAM  ******************************
00D2         	NOTSEQ		; NOTE POINTER
             		*=*+1
00D3         	REPSEQ			; HOW MANY TIMES TO REPEAT
             		*=*+1
00D4         	NDURAT			; DURAT OF NOTE
             		*=*+1
00D5         	SDURAT			; DURAT OF SPACE
             		*=*+1
00D6         	NPRIOR			; PRIOR OF NOE TYPE
             		*=*+1
00D7         	REPPTR			; WHERE TO REPEAT IN NOTETB
             		*=*+1
00D8         	NDURTM			; NOTE TIMER
             		*=*+1
00D9         	NOTVOL			; NOTE VOLUME
             		*=*+1
00DA         	PHOREP			; REPEAT NOTE FOR PHOTON
             		*=*+1
00DB         	AUDEXP			; EXPLOS SERVICE TIMER
             		*=*+1
00DC         	ATYPE2		; RAM FO AUDC2
             		*=*+1
00DD         	ATYPE3			; RAM FOR AUDC3
             		*=*+1
00DE         	AFREQ1			; RAM FO AUDF1
             		*=*+1
00DF         	AFREQ2			; RAM FOR AUDF2
             		*=*+1
00E0         	AUDADD			; HOW MUCH TO ADD
             		*=*+1
00E1         	AUDTIM		; AUDIO TIMEOUT  0=ALL DONE
             		*=*+1
00E2         	EXPDEL			; EXPLOS DELAY
             		*=*+1
00E3         	BIGEXP			; SHIELDS DOWN EXPLOS
             		*=*+1
             	;	***********************************************************
             	;	***************  OBJECT RAM  ******************************
00E4         	GRAPH		; GRAPHIC FOR OBJO-4
             		*=*+5
00E9         	STFLAG		; 0=OBJECT NOT ON (DEFINED IN THINK, OR PHOTON)
             		*=*+5
             	;	**************************************************************
             	;	******************  COLOR RAM  ****************************
00EE         	COLRAM		; PLAYER AND PLAYFIELD COLOR RAM
             		*=*+14
             	;	**********************************************************
00FC         	PHASE4
             	;

             	;
             	;	ADDRESS SPACE
             	;
             	;
             	;	COLLEEN MNEMONICS
             	;
D200         	POKEY	=	$D200
D200         	POT0	=	POKEY+0
D201         	POT1	=	POKEY+1
D202         	POT2	=	POKEY+2
D203         	POT3	=	POKEY+3
D204         	POT4	=	POKEY+4
D205         	POT5	=	POKEY+5
D206         	POT6	=	POKEY+6
D207         	POT7	=	POKEY+7
D208         	ALLPOT	=	POKEY+8
D209         	KBCODE	=	POKEY+9
D20A         	RANDOM	=	POKEY+10
D20D         	SERIN	=	POKEY+13
D20E         	IRQST	=	POKEY+14
D20F         	SKSTAT	=	POKEY+15
D200         	AUDF1	=	POKEY+0
D201         	AUDC1	=	POKEY+1
D202         	AUDF2	=	POKEY+2
D203         	AUDC2	=	POKEY+3
D204         	AUDF3	=	POKEY+4
D205         	AUDC3	=	POKEY+5
D206         	AUDF4	=	POKEY+6
D207         	AUDC4	=	POKEY+7
D208         	AUDCTL	=	POKEY+8
D209         	STIMER	=	POKEY+9
D20A         	SKRES	=	POKET+10
D20B         	POTGO	=	POKEY+11
D20D         	SEROUT	=	POKEY+13
D20E         	IRQEN	=	POKEY+14
D20F         	SKCTL	=	POKEY+15
             	;
D000         	CTIA	=	$D000
D000         	HPOSP0	=	CTIA+0
D001         	HPOSP1	=	CTIA+1
D002         	HPOSP2	=	CTIA+2
D003         	HPOSP3	=	CTIA+3
D004         	HPOSM0	=	CTIA+4
D005         	HPOSM1	=	CTIA+5
D006         	HPOSM2	=	CTIA+6
D007         	HPOSM3	=	CTIA+7
D008         	SIZEP0	=	CTIA+8
D009         	SIZEP1	=	CTIA+9
D00A         	SIZEP2	=	CTIA+10
D00B         	SIZEP3	=	CTIA+11
D00C         	SIZEM	=	CTIA+12
D00D         	GRAFP0	=	CTIA+13
D00E         	GRAFP1	=	CTIA+14
D00F         	GRAFP2	=	CTIA+15
D010         	GRAFP3	=	CTIA+16
D011         	GRAFM	=	CTIA+17
D012         	COLPM0	=	CTIA+18
D013         	COLPM1	=	CTIA+19
D014         	COLPM2	=	CTIA+20
D015         	COLPM3	=	CTIA+21
D016         	COLPF0	=	CTIA+22
D017         	COLPF1	=	CTIA+23
D018         	COLPF2	=	CTIA+24
D019         	COLPF3	=	CTIA+25
D01A         	COLBK	=	CTIA+26
D01B         	PRIOR	=	CTIA+27
D01C         	VDELAY	=	CTIA+28
D01D         	GRACTL	=	CTIA+29
D01E         	HITCLR	=	CTIA+30
D01F         	CONSOL	=	CTIA+31
D000         	M0PF	=	CTIA+0
D001         	M1PF	=	CTIA+1
D002         	M2PF	=	CTIA+2
D003         	M3PF	=	CTIA+3
D004         	P0PF	=	CTIA+4
D005         	P1PF	=	CTIA+5
D006         	P2PF	=	CTIA+6
D007         	P3PF	=	CTIA+7
D008         	M0PL	=	CTIA+8
D009         	M1PL	=	CTIA+9
D00A         	M2PL	=	CTIA+10
D00B         	M3PL	=	CTIA+11
D00C         	P0PL	=	CTIA+12
D00D         	P1PL	=	CTIA+13
D00E         	P2PL	=	CTIA+14
D00F         	P3PL	=	CTIA+15
D010         	TRIG0	=	CTIA+16
D011         	TRIG1	=	CTIA+17
D012         	TRIG2	=	CTIA+18
D013         	TRIG3	=	CTIA+19
             	;
D400         	ANTIC	=	$D400
D400         	DMACTL	=	ANTIC+0
D401         	CHACTL	=	ANTIC+1
D402         	DLISTL	=	ANTIC+2
D403         	DLISTH	=	ANTIC+3
D404         	HSCROL	=	ANTIC+4
D405         	VSCROL	=	ANTIC+5
D407         	PMBASE	=	ANTIC+7
D409         	CHBASE	=	ANTIC+9
D40A         	WSYNC	=	ANTIC+10
D40B         	VCOUNT	=	ANTIC+11
D40C         	PENH	=	ANTIC+12
D40D         	PENV	=	ANTIC+13
D40E         	NMIEN	=	ANTIC+14
D40F         	NMIRES	=	ANTIC+15
D40F         	NMIST	=	ANTIC+15
D300         	PIA	=	$D300
D300         	PORTA	=	PIA+0
D301         	PORTB	=	PIA+1
D302         	PACTL	=	PIA+2
D303         	PBCTL	=	PIA+3
             	;
             	;		OPERATING SYSTEM
             	;
0216         	VIMIRQ	=	$0216		; IMMEDITATE IRQ LOCATION
0222         	VVBLKI	=	$0222		; IMMEDIATE VERT BLANK NMI VECTOR
0200         	VDSLST	=	$0200		; DISPLAY LIST NMI VECTOR
E000         	ALPHA	=	$E000
             	;

             	;			EQUATES
0282         		DISPL1	=	DISPLY+2		; LDISP
028F         		DISPL2	=	DISPLY+15		; LDISP
02DF         		DISPL3	=	DISPLY+95		; LDISP
007C         		DISTOP	=	$7C		; LDISP SUB
0032         		VOFLOW	=	50
0032         		VSTCEN	=	50
007A         		VOBCEN	=	$7A
0050         		HOFLOW	=	80
0050         		HSTCEN	=	80
007D         		HOBCEN	=	$7D
0051         		SCPTAB	=	81		; FOR LOADING PTAB
0064         		SBCD	=	100		; FOR LOADING BCDCON
0028         		SCVCON	=	40		; FOR LOADING VCON TABLES
1D40         		ICON1	=	$1D40
1BFE         		ICON2	=	$1BFE
003D         		HORCHT	=	$3D		; HOR EDGE OF CHART
003F         		VERCHT	=	$3F		; VERT EDGE OF CHART
000C         		STRNUM	=	12		; NUMBER OF STARS DISPLAYED
0005         		OBJNUM	=	5		; NUMBER OF OBJECTS
0020         		EXPNUM	=	32		; NUMBER OF EXPLOSION STARS
0031         		RAMNUM	=	OBJNUM+STRNUM+EXPNUM	; TOTAL NUMBER OF RAM LOC.
0004         		OBLAST	=	OBJNUM-1	; RAM LOC OF LAST OBJECT
0030         		RMLAST	=	RAMNUM-1	; RAM LOC OF LAST STAR IN EXPLOSION
0010         		STLAST	=	OBJNUM+STRNUM-1	; RAM LOC OF LAST STAR IN REAL STRS
0002         		OBPHOT	=	OBJNUM-3	; LAST PHOTON LOCATION
0003         		OBCOMP	=	OBJNUM-2	; LAST PHOTON WHIC COULD BE COMP CONT.
1B36         		INSET	=	$1B36		; IST BYTE OF INSET
0064         		VMAX	=	100
00A0         		HMAX	=	160		; MAX HORIZ STAR POSITION DISPLAYED
             	;
00A0         		DBLUE	=	$A0		; DARK BLUE
0044         		RED	=	$44		; COLOR
0092         		LTBLUE	=	$92		; COLOR
00AF         		BRTBLU	=	$AF		; COLOR
004F         		BRTRED	=	$4F		; COLOR
0060         		DRKRED	=	$60		; COLO
0042         		DIMRED	=	$42		; COLOR
0090         		DIMBLU	=	$90		; COLOR
0026         		YELLOW	=	$26		; COLOR
0055         		DIM	=	$55		; MEMMAP CODE FOR DIM STAR
00AA         		MED	=	$AA
00FF         		BRT	=	$FF
0040         		IRQMSK	=	$40		; KEY INTERRUPT MASK
17E3         		NOSTAR	=	$17E3		; NO STAR DUING ATRACT
             	;
             	;
             	;		CHARACTER GRAPHICS
             		*=$A000
             	;
             	;
A000         	CGRAPH
A000 00 7F 47	C0	.BYTE	00,$7F,$47,$47,$47,$47,$47,$7F
A003 47 47 47	
A006 47 7F   	
A008 00 30 10	C1	.BYTE	00,$30,$10,$10,$10,$38,$38,$38
A00B 10 10 38	
A00E 38 38   	
A010 00 78 08	C2	.BYTE	00,$78,$08,$08,$78,$40,$40,$78
A013 08 78 40	
A016 40 78   	
A018 00 78 08	C3	.BYTE	00,$78,$08,$08,$7C,$0C,$0C,$7C
A01B 08 7C 0C	
A01E 0C 7C   	
A020 00 60 60	C4	.BYTE	00,$60,$60,$60,$6C,$7C,$0C,$0C
A023 60 6C 7C	
A026 0C 0C   	
A028 00 78 40	C5	.BYTE	00,$78,$40$,40,$78,$08,$08,$78
A02B 40 78 08	
A02E 08 78   	
A030 00 78 48	C6	.BYTE	00,$78,$48,$40,$40,$7E,$42,$7E
A033 40 40 7E	
A036 42 7E   
A038 00 7C 44	C7	.BYTE	00,$7C,$44,$04,$1C,$10,$10,$10
A03B 04 1C 10	
A03E 10 10   	
A040 00 38 28	C8	.BYTE	00,$38,$28,$28,$7C,$6C,$6C,$7C
A043 28 7C 6C	
A046 6C 7C   	
A048 00 7C 44	C9	.BYTE	00,$7C,$44,$44,$7C,$0C,$0C,$0C
A04B 44 7C 0C	
A04E 0C 0C   
A050 00 00 00	CBLK	.BYTE	0,0,0,0,0,0,0,0
A053 00 00 00	
A056 00 00   	
A058 38 38 38	CEQ	.BYTE	$38,$38,$38,$00,$00,$38,$38,$38
A05B 00 00 38	
A05E 38 38   	
A060 80 80 80	CQCBLK	.BYTE	$80,$80,$80,$80,$80,$80,$80,$FF
A063 80 80 80	
A066 80 FF   	
A068 00 3C 20	CE	.BYTE	$00,$3C,$20,$20,$78,$60,$60,$7C
A06B 20 78 60	
A06E 60 7C   	
A070 00 66 99	CINF	.BYTE	$00,$66,$99,$99,$99,$66,$00,$00
A073 99 99 66	
A076 00 00   	
A078 00 00 00	CMINUS	.BYTE	$00,$00,$00,$7E,$00,$00,$00,$00
A07B 7E 00 00	
A07E 00 00   	
A080 00 18 18	CPLUS	.BYTE	$00,$18,$18,$7E,$18,$18,$18
A083 18 7E 18	
A086 18 18   	
A088 00 18 7E	CPHI	.BYTE	$00,$18,$7E,$DB,$99,$DB,$7E,$18
A08B DB 99 DB	
A08E 7E 18   	
A090 66 66 66	CV	.BYTE	$66,$66,$66,$66,$66,$2C,$38,$30
A093 66 66 2C	
A096 38 30   	
A098 00 7C 44	CRHO	.BYTE	0,$7C,$44,$44,$7C,$68,$6C,$6C
A09B 44 7C 68	
A09E 6C 6C   	
A0A0 00 1C 3E	CTETA	.BYTE	$00,$1C,$3E,$63,$5D,$63,$3E,$1C
A0A3 63 5D 63	
A0A6 3E 1C   	
A0A8 00 46 46	CK	.BYTE	$00,$46,$46,$44,$7C,$64,$66,$66
A08B 44 7C 64	
A08E 66 66   	
A0B0 FE 92 10	CT	.BYTE	$FE,$92,$10,$18,$18,$18,$18,$18
A0B3 18 18 18	
A0B6 18 18   	
A0B8 FC 8C 8C	CC	.BYTE	$FC,$8C,$8C,$80,$80,$80,$84,$FC
A0BB 80 80 80	
A0BE 84 FC   	
A0C0 00 00 00	CHLINE	.BYTE	0,0,0,0,0,0,0,$FF
A0C3 00 00 00	
A0C6 00 FF   	
A0C8 80 80 80	CVLINE		.BYTE	$80,$80,$80,$80,$80,$80,$80,$80
A0CB 80 80 80	
A0CE 80 80   	
A0D0 00 00 00	CDOT		.BYTE	0,0,0,0,0,0,0,$80
A0D3 00 00 00	
A0D6 00 80   	
A0D8 80 AA 9C	CSBASE		.BYTE	$80,$AA,$9C,$BE,$9C,$AA,$80,$FF
A0DB BE 9C AA	
A0DE 80 FF   	
A0E0 80 8E 80	CZY2		.BYTE	$80,$98,$90,$B6,$B0,$BC,$80,$FF
A0E3 B6 80 8C	
A0E6 80 FF   	
A0E8 80 8E 80	CZY1		.BYTE	$80,$8E,$80,$B8,$80,$9C,$80,$FF
A0EB B8 80 9C	
A0EE 80 FF   	
A0F0 80 B0 98	CZY3		.BYTE	$80,$B0,$98,$BE,$98,$B0,$80,$FF
A0F3 BE 98 B0	
A0F6 80 FF   	
             	;
             	;
A0F8         	SESCAN
A0F8 00 00 6C		 .BYTE	 0,0,$6C,$6F,$6E,$67,0,$72,$61,$6E,$67,$65,0,$73,$63,$61,$6E
A0FB 6F 6E 67	
A0FE 00 72 61	
A101 6E 67 65	
A104 00 73 63	
A107 61 6E   	
A109         	BACKUP
A109 00 00 00		 .BYTE	 0,0,0,0,0,0,$61,$66,$74,0,$76,$69,$65,$77,0,0,0
A10C 00 00 00	
A10F 61 66 74	
A112 00 76 69	
A115 65 77 00	
A118 00 00   	
             	;
A11A         	GALCHT
A11A 00 00   		 .BYTE 0,0
A11C 00 67 61		 .BYTE	 0,$67,$61,$6C,$61,$63,$74,$69,$63,0,$63,$68,$61,$72,$74,0
A11F 6C 61 63	
A122 74 69 63	
A125 00 63 68	
A128 61 72 74	
A12B 00      	
A12C 00 00   		 .BYTE	 0,0
             	;
             	;
             	;
A12E         	GLDISP		 ; GAL CHT DISPLAY LIST
A12E 60 46   		 .BYTE	 $60,$46
A130 1A A1   		 .WORD	 GALCHT
A132 F0 47   		 .BYTE	 $F0,$47
A134 35 0D   		 .WORD	 CHTDIS
A136 07 07 07		 .BYTE	 7,7,7,7,7,7,7,7$80,$46
A139 07 07 07	
A13C 07 07 80	
A13F 46      	
A140 14 0D   		 .WORD	 MESAGE
A142 46      		 .BYTE	 $46
A143 71 09   		 .WORD	 DGALAC
A145 06 06 41		 .BYTE	 6,6,$41
A148 80 02   		 .WORD	 DISPLY
             	;
             	;
A14A         	PHASE8
             	;
             	;
             	;		INIT SECTION
             	;
A14A         	INIT
A14A A9 00   		LDA	#$00
A14C 8D 0F D2		STA	SKCTL
A14F 85 66   		STA	TIMOUT		; RESET TIMEOUT
A151 85 66   		STA	MISDIF		; MISSIONDIFFICULTY
A153 85 63   		STA	RESET		; ONE SHOT CONSOL
A155 A9 03   		LDA	#$03
A157 8D 0F D2		STA	SKCTL		; TURN POKEY ON
             	;
A15A         	INIT3		; GAME SELECT, RESTART POINT  ****************************
A15A A0 24   		LDY	#SENATA-SENTAB
             	;
A15C         	INIT4		; ATTRACT MODE RESTART POINT  **************************
A15C A9 FF   		LDA	#$FF		; GAME OVER
             	;
A15E         	INIT1		; GAME START RESTART POINT  ************************
A15E 84 65   		STY	REPMSG
A160 85 64   		STA	ATRACT
             	;	CLEAR I/O
A162 A9 00   		LDA	#$00
A164 AA      		TAX
A165         	INIT2
A165 9D 00 D0		STA	CTIA,X
A168 9D 00 D4		STA	ANTIC,X
A16B E0 0F   		CPX	#$0F		; DONT RESET POKEY
A16D B0 03   		BCS	INIT5
A16F 9D 00 D2		STA	POKEY,X
A172         	INIT5
A172 9D 00 D3		STA	PIA,X
A175 9D      		.BYTE	$9D		; STA ABS,X
A176 67 00   		.WORD	PAGE0		; STA PAGE0,X  (ABSOLUTE)
A178 E8      		INX
A179 D0 EA   		BNE INIT2
             	;			I/O CLEARED
             	;
             	;
A17B CA      		DEX		; X=FF
A17C 9A      		TXS		; LOAD STACK PNTR
A17D DB      		CLD
             	;
A17E A9 02   		LDA	#RAMMAP/256
A180 20 0F AE		JSR	CLRMP1		; CLEAR ALL RAM
             	;		LD VECTOR RAM
A183 A9 51   		LDA	#IRQVEC
A185 8D 16 02		STA	VIMIRQ
A188 A9 A7   		LDA	#IRQVEC/256
A18A 8D 17 02		STA	VIMIRQ+1
A18D A9 D1   		LDA	#VBNMI
A18F 8D 22 02		STA	VVBLKI
A192 A9 18   		LDA	#DISNMI
A194 8D 00 02		STA	VDSLST
A197 A9 A6   		LDA	#VBNMI/256
A199 8D 23 02		STA	VVBLKI+1
A19C A9 A7   		LDA	#DISNMI/256
A19E 8D 01 02		STA	VDSLST+1
             	;
             	;

             	;			CONFIGURE PIA
             	;
A1A1 A9 04   		LDA	#$04
A1A3 8D 02 D3		STA	PACTL		; TURN ON JOYSTICK
             	;
             	;
             	;
             	;
             	;		CONFIGURE CTIA
             	;
A1A6 A9 11   		LDA	#$11
A1A8 8D 1B D0		STA	PRIOR
             	;
A1AB A9 03   		LDA	#$03
A1AD 8D 1D D0		STA	GRACTL
             	;
A1B0 20 BA B3		JSR	LDTABS		; INIT TABLES
             	;
             	;
             	;			INIT DISPLAY LIST
A1B3 A2 0A   		LDX	#$0A		; KEY F, FRONT DISPLAY
A1B5 20 45 B0		JSR	KEYS15		; INIT FRONT VIEW
A1B8 A5 64   		LDA	ATRACT
A1BA 29 80   		AND	#$80
A1BC A8      		TAY
A1BD A2 5F   		LDX	#DISPL3-DISPLY
A1BF A9 08   		LDA	#$08
A1C1 20 F1 AD		JSR	LDISP		; SHIP ALIVE OR DEAD
             	;
A1C4 A9 20   		LDA	#$20
A1C6 85 71   		STA	WARP		; WARP 5 SPEED
             	;
             	;
             	;			CONFIGURE ANTIC
             	;
A1C8 A9 80   		LDA	#DISPLY
A1CA 8D 02 D4		STA	DLISTL
A1CD A9 02   		LDA	#DISPLY/256
A1CF 8D 03 D4		STA	DLISTH
A1D2 A9 3E   		LDA	#$3E
A1D4 8D 00 D4		STA	DMACTL		; DMA ON
             	;
A1D7 A9 00   		LDA	#PGRAPH-$0300/256
A1D9 8D 07 D4		STA	PMBASE			; LD PLAYER / MISSLE BASE
             	;
             	;
             	;
             	;
             	;		INIT NUMBER OF STARS
A1DC A9 10   		LDA	#STLAST
A1DE 85 79   		STA	NSTARS
             	;
             	;
A1E0 A6 62   		LDX	MISDIF		; GAME TYPE MESSAGE
A1E2 BC 0C BF		LDY	MSENTB,X
A1E5 20 23 B2		JSR	LDMESS
             	;
             	;
             	;
             	;
             	;
             	;		ENABLE INTERRUPTS
A1E8 A9 40   		LDA	#IRQMSK
A1EA 8D 0E D2		STA	IRQEN
A1ED 58      		CLI		; IRQS READY
A1EE A9 C0   		LDA	#$C0
A1F0 8D 0E D4		STA	NMIEN		; NMIS READY
             	;
             	;		END INIT
             	;
             		;		MAIN PROGRAM
A1F3         	MAIN
             	;
             	;		MAIN FLOW CHART
             	;	START
             	;		WAIT FOR VBLANK				
             	;		CLEAR AND LOAD STARS/OBJECTS		
             	;		MOVE ROUTINES				
             	;		PLAYER INTERFACE SECTION		GAME ON ONLY
             	;		SERVICE SECTION				GAME ON ONLY
             	;		HIT DETECT				GAME ON ONLY
             	;		SERVICE CONTINUOUS RUNNING ROUTINES
             	;	JUMP TO START
             	;
             	;
A1F3 A5 67   		LDA	PROGST
A1F5 F0 FC   		BEQ	MAIN			 ; WAIT FOR VBLANK NMI
A1F7 A9 00   		LDA	#$00			 ; RESET VBLANK STATUS REGISTER
A1F9 85 67   		STA	PROGST
             	;
             	;
             	;
             	;
             	;
             	;		UPDATE MEMORY MAP RAM AND PLAYERS RAM
             	;
             	;		CLRSTR
             	;		CLEAR STAR ROUTINE
A1FB A5 7A   		LDA	CNSTAR		; THIS FLAGS SAYS OLDPS NOT DEFINED IF=00
A1FD F0 20   		BEQ	CLRSR2
A1FF A2 04   		LDX	#OBLAST		; LAST LOCATION OF OBJECT IN RAM
A201         	CLRSR1
A201 E8      		INX
A202 BC 5B 0C		LDY	OLDVER,X
A205 B9 00 08		LDA	VCONL,Y
A208 85 68   		STA	PNTR
A20A B9 64 08		LDA	VCONH,Y
A20D 85 69   		STA	PNTR+1
A20F BC 8C 0C		LDY	OLDHOR,X
A212 BD BD 0C		LDA	OLDBYT,X
A215 91 68   		STA	(PNTR),Y	; BYTE RESTORED
A217 E4 7A   		CPX	CNSTAR
S219 90 E6   		BCC	CLRSR1
A21B A9 00   		LDA	#$00
A21D 85 7A   		STA	CNSTAR		; STARS CLEARED
A21F         	CLRSR2
             	;
             	;
             	;		STOSTR
             	;
             	;	STORE STAR IN RAM MAP ROUTINE
             	;
A21F A5 C0   		LDA	HFLAG		; IN HYPER JUMP  ?
A221 30 2D   		BMI	STOSR1			; YES , NO STORE.
             	;
             	;
             	;
A223 A6 79   		LDX	NSTARS	; LAST BYTE OF STAR RAM TO STORE
A225 86 7A   		STX	CNSTAR		; STARS POINTERS DEFINED OK TO CLEAR NOW
A227         	STOSR2

             	;
A227 BD F9 0B		LDA	VPOS,X
A22A 9D 5B 0C		STA	OLDVER,X
A22D A8      		TAY
A22E B9 00 08		LDA	VCONL,Y
A231 85 68   		STA	PNTR
A233 B9 64 08		LDA	VCONH,Y
A236 85 69   		STA	PNTR+1
A238 BD 2A 0C		LDA	HPOS,X
A23B 4A      		LSR	A
A23C 4A      		LSR	A
A23D 9D 8C 0C		STA	OLDHOR,X
A240 A8      		TAY
A241 B1 68   		LDA	(PNTR),Y
A243 9D BD 0C		STA	OLDBYT,X		; BYTE SAVED
A236 1D EE 0C		ORA	STRBYT,X
A249 91 68   		STA	(PNTR),Y
             	;
A24B CA      		DEX
A24C E0 04   		CPX	#OBLAST
A24E D0 07   		BNE	STOSR2		; DO NEXT STAR
A250         	STOSR1
A250 A5 66   		LDA	TIMOUT
A252 10 0E   		BPL	STOSR3
A254 A9 00   		LDA	#$00
A256 8D E3 17		STA	NOSTAR
A259 8D E4 17		STA	NOSTAR+1
A25C 8D BC 17		STA	NOSTAR-39
A25F 8D BB 17		STA	NOSTAR-40
A262         	STOSR3
             	;
             	;
             	;		CLROBJ
             	;		CLEAR OBJECT RAM
             	;	OBJECT 4
A262 A9 00   		LDA	#$00
A264 AC 5F 0C		LDY	OLDVER+4
A267 AE C1 0C		LDX	OLDNUM+4
A26A         	CLROB1
A26A 99 00 03		STA	MGRAPH,Y
A26D C8      		INY
A26E CA      		DEX
A26F 10 F9   		BPL	CLROB1
             	;		OBJECT 3
A271 AC 5E 0C		LDY	OLDVER+3
A274 AE C0 0C		LDX	OLDNUM+3
A277         	CLROB2
A277 99 00 07		STA	PGRAP3,Y
A27A C8      		INY
A27B CA      		DEX
A27C 10 F9   		BPL	CLROB2
             	;		OBJECT 2
A27E AC 5D 0C		LDY	OLDVER+2
A281 AE BF 0C		LDX	OLDNUM+2
A284         	CLROB3
A284 99 00 06		STA	PGRAP2,Y
A287 C8      		INY
A288 CA      		DEX
A289 10 F9   		BPL	CLROB3
             	;		OBJECT 1
A28B AC 5C 0C		LDY	OLDVER+1
A28E AE BE 0C		LDX	OLDNUM+1
A291         	CLROB4
A291 99 00 05		ATS	PGRAP1,Y
A294         		INY
A295         		DEX
A296 10 F9   		BPL	CLROB4
             	;		OBJECT 0
A298 AC 5B 0C		LDX	OLDVER+0
A29B AE BD 0C		LDX	OLDNUM+0
A29E         	CLROB5
A29E 99 00 04		STA	PGRAP0,Y
A2A1 C8      		INY
A2A2 CA      		DEX
A2A3 10 F9   		BPL	CLROB5
             	;
             	;
             
             	;		STOOBJ
             	;		STORE OBJECT ROUTINE
             	;
             	;	OBJECT 4, ALWAYS PHOTON, OR DOCKING OBJECT
A2A5 AD 90 0C		LDA	GINDEX+4
A2A8 C9 01   		CMP	#$01		; DEFINE CARRY
A2AA A4 E8   		LDY	GRAPH+4
A2AC AE FD 0B		LDX	VPOS+4
A2AF 8E 5F 0C		STX	OLDVER+4
A2B2 AD F2 0C		LDA	NUMBYT+4
A2B5 85 6A   		STA	TEMP
A2B7 8D C1 0C		STA	OLDNUM+4
A2BA         	STOOB1
A2BA B9 E4 B8		LDA	PHGRAF,Y
A2BD B0 03   		BCS	STOOB8
A2BF 2D 0A D2		AND	RANDOM
A2C2         	STOOB8
A2C2 9D 00 03		STA	MGRAPH,X
A2C5 C8      		INY
A2C6 E8      		INX
A2C7 C6 6A   		DEC	TEMP
A2C9 10 EF   		BPL	STOOB1
             	;	OBJECT 3 , ALWAYS PHOTON
A2CB AD 8F 0C		LDA	GINDEX+3
A2CE C9 01   		CMP	#$01
A2D0 A4 E7   		LDY	GRAPH+3
A2D2 AE FC 0B		LDX	VPOS+3
A2D5 8E 5E 0C		STX	OLDVER+3
A2D8 AD F1 0C		LDA	NUMBYT+3
A2DB 85 6A   		STA	TEMP
A2DD 8D C0 0C		STA	OLDNUM+3
A2E0         	STOOB2
A2E0 B9 E4 B8		LDA	PHGRAF,Y
A2E3 B0 03   		BCS	STOOB9
A2E5 2D 0A D2		AND	RANDOM
A2E8         	STOOB9
A2E8 9D 00 07		STA	PGRAP3,X
A2EB E8      		INX
A2EC C8      		INY
A2ED C6 6A   		DEC	TEMP
A2EF 10 EF   		BPL	STOOB2
             	;	OBJECT 2, (VARIABLE GRAPHIC)
A2F1 AD 8E 0C		LDA	GINDEX+2
A2F4 C9 01   		CMP	#$01		; DEFINE CARRY
A2F6 A4 E6   		LDY	GRAPH+2
A2F8 AE FB 0B		LDX	VPOS+2
A2FB 8E 5D 0C		STX	OLDVER+2
A2FE AD F0 0C		LDA	NUMBYT+2
A301 85 6A   		STA	TEMP
A303 8D BF 0C		STA	OLDNUM+2
A306         	STOOB3
A306 B9 E4 B8		LDA	PHGRAF,Y
A309 B0 03   		BCS	STOOB7
A30B 2D 0A D2		AND 	RANDOM
A30E         	STOOB7
A30E 9D 00 06		STA	PGRAP2,X
A311 E8      		INX
A312 C8      		INY
A313 C6 6A   		DEC	TEMP
A315 10 EF   		BPL	STOOB3
             	;		OBJECT 1 (VARIABLE)
A317 A4 E5   		LDY	GRAPH+1
A319 AE FA 0B		LDX	VPOS+1
A31C 8E 5C 0C		STX	OLDVER+1
A31F AD EF 0C		LDA	NUMBYT+1
A322 85 6A   		STA	TEMP
A324 8D BE 0C		STA	OLDNUM+1
A327         	STOOB5
A327 B9 B1 B9		LDA	ZYGRAP,Y
A32A 9D 00 05		STA	PGRAP1,X
A32D E8      		INX
A32E C8      		INY
A32F C6 6A   		DEC	TEMP
A331 10 F4   		BPL	STOOB5
            	;			OBJECT 0 (VARIABLE)
A333 A4 E4   		LDY	GRAPH+0
A335 AE F9 0B		LDX	VPOS+0
A338 8E 5B 0C		STX	OLDVER+0
A33B AD EE 0C		LDA	NUMBYT+0
A33E 85 6A   		STA	TEMP
A340 8D BD 0C		STA	OLDNUM+0
A343         	STOOB6
A343 B9 B1 B9		LDA	ZYGRAF,Y
A346 9D 00 04		STA	PGRAP0,X
A349 E8      		INX
A34A C8      		INY
A34B C6 6A   		DEC	TEMP
A34D 10 F4   		BPL	STOOB6
             	;
             	;		UPDATE HORIZ
             	;
A34F AD 2A 0C		LDA	HPOS+0
A352 8D 00 D0		STA	HPOSP0+0
A355 AD 2B 0C		LDA	HPOS+1
A358 8D 01 D0		STA	HPOSP0+1
A35B AD 2C 0C		LDA	HPOS+2
A35E 8D 02 D0		STA	HPOSP0+2
A361 AD 2D 0C		LDA	HPOS+3
A364 8D 03 D0		STA	HPOSP0+3
A367 AD 2E 0C		LDA	HPOS+4
A36A 8D 07 D0		STA	HPOSP0+7
A36D 18      		CLC
A36E 69 02   		ADC	#$02
A370 8D 06 D0		STA	HPOSP0+6
A373 69 02   		ADC	#$02
A375 8D 05 D0		STA	HPOSP0+5
A378 69 02   		ADC	#$02
A37A 8D 04 D0		STA	HPOSP0+4
             	
             	;
             	;		END UPDATE MEMORY MAP RAM AND PLAYERS RAM
             	;
             	;
             	;
             	;
             	;	STARS/OBJECTS MOVE ROUTINES
A37D 24 D0   		BIT	DISFLG
A37F 30 3A   		BMI	MAINI		; NO ROTATE IN GALACTIC CHART
             	;
             	;		YROTAT
             	;		ROTATE ALL LEFT AND RIGHT
A381 A5 C8   		LDA	HORJOY		; HORIZ JOYSTICK ?
A383 F0 19   		BEG	YROTA1		; NO
A385 85 6D   		STA	TEMP3
A387 A4 79   		LDY	NSTARS		; LAST BYTE OF STARS
A389         	YROTA2
A389 84 6E   		STY	TEMP4		; TEMP STORE
A38B 18      		CLC
A38C 9B      		TYA
A38D AA      		TAX
A38E 69 31   		ADC	#RAMNUM		; YPOS
A390 A8      		TAY
A391 20 9B B6		JSR	ROHELP
A394 98      		TYA
A395 AA      		TAX
A396 A4 6E   		LDY	TEMP4
A398 20 9B B6		JSR	ROHELP
A39B 88      		DEY
A39C 10 EB   		BPL	YROTA2
A39E         	YROTA1
             	;
             	;
             	;
             	;		ZROTAT
             	;		ROTATE ALL UP AND DOWN
A39E A5 C9   		LDA	VERJOY		; VERT JOYSTICK ?
A3A0 F0 19   		BEQ	ZROTA1		; NO
A3A2 85 6D   		STA	TEMP3
A3A4 A4 79   		LDY	NSTARS
A3A6         	ZROTA2
A3A8 84 6E   		STY	TEMP4
A3A8 18      		CLC
A3A9 98      		TYA
A3AA AA      		TAX
A3AB 69 62   		ADC	#RAMNUM*2		; ZOPS
A3AD A8      		TAY
A3AE 20 9B B6		JSR	ROHELP
A3B1 98      		TYA
A3B2 AA      		TAX
A3B3 A4 6E   		LDY	TEMP4
A3B5 20 9B B6		JSR	ROHELP
A3B8 88      		DEY
A3B9 10 EB   		BPL	ZROTA2
A3BB         	ZROTA1
             	;
             	;
A3BB         	MAIN1
             	;		XMOVER
             	;		UPDATE ALL XPOS DUE TO FORWARD SHIP MOTION
             	;		SUBTRACT SPEED FROM XPOS
A3BB A6 79   		LDX	NSTARS		; X=INDEX TO STARS/POBJECT TO UPDATE
A3BD         	XMOVE1
A3BD E0 05   		CPX	#OBJNUM		; PHOTONS ?
A3BF B0 05   		BCS	XMOVE2		; NO.
A3C1 BD BC 0C		LDA	GINDEX,X
A3C4 F0 19   		BEQ	XMOVE3
A3C6         	XMOVE2
A3C6 38      		SEC
A3C7 BD D3 0A		LDA	XPOSL,X
A3CA E5 70   		SBC	SPEED
A3CC 9D D3 0A		STA	XPOSL,X
A3CF BD 40 0A		LDA	XPOSH,X
A3D2 E5 C1   		SBC	HISPED
A3D4 9D 40 0A		STA	XPOSH,X
A3D7 BD AD 09		LDA	XSIGN,X
A3DA E9 00   		SBC	#$00		; CARRY ONLY
A3DC 9D AD 09		STA	XSIGN,X
A3DF         	XMOVE3
A3DF CA      		DEX
A3E0 10 DB   		BPL	XMOVE1		; NEXT STAR
             	;		ALL DONE
             	;
             	;

             	;		MOTION
             	;	OTHER MOTION SUCH AS DUE TO ZYLON SHIP POWER
             	;	                                OR PHOTONS
             	;	XINCRE,YINCRE,ZINCRE ARE ALL SIGN-MAGNITUDE TYPES
A3E2 A6 79   		LDX	NSTARS
A3E4         	MOTIN1
A3E4 E0 10   		CPX	#STLAST		; REG STARS ?
A3E6 D0 02   		BNE	MOTIN9		; NO
A3E8 A2 04   		LDX	#OBLAST		; LAST OBJ
A3EA         	MOTIN9
A3EA 8A      		TXA
A3EB         	MOTIN2
A3EB A8      		TAY
A3EC A9 00   		LDA	#$00
A3EE 85 6B   		STA	TEMP1
A3F0 B9 66 0B		LDA	XINCRE,Y
A3F3 10 09   		BPL	MOTIN3
A3F5 49 7F   		EOR	#$7F
A3F7 18      		CLC
A3F8 69 01   		ADC	#$01
A3FA B0 02   		BCS	MOTIN3
A3FE         	MOTIN3
A3FE 18      		CLC
A3FF 79 D3 0A		ADC	XPOSL,Y
A402 99 D3 0A		STA	XPOSL,Y
A405 B9 40 0A		LDA	XPOSH,Y
A408 65 6B   		ADC	TEMP1
A40A 99 40 0A		STA	XPOSH,Y
A40D B9 AD 09		LDA	XSIGN,Y
A410 65 6B   		ADC	TEMP1
A412 99 AD 09		STA	XSIGN,Y
             	;
A415 98      		TYA
A416 18      		CLC
A417 69 31   		ADC	#RAMNUM
A419 C9 90   		CMP	#RMLAST*3	; ALL DONE ?
A41B 90 CE   		BCC	MOTIN2		; NO
A41D CA      		DEX
A41E 10 C4   		BPL	MOTIN1		; NEXT STAR OR OBJECT
             	;
             	;

             	;		BOUNDS
             	;
A420 A0 04   		LDY	#OBLAST		; ONLY OBJECTS
A422         	BOUND1
A422 98      		TYA
A423 AA      		TAX
A424 A9 02   		LDA	#$02
A426 85 6A   		STA	TEMP
A428         	BOUND3
A428 BD AD 09		LDA	XSIGN,X
A42B C9 02   		CMP	#$02
A42D 90 10   		BCC	BOUND4
             	;		OUT OF BOUNDS
A42F 0A      		ASL	A
A430 A9 00   		LDA	#$00
A432 9D AD 09		STA	XSIGN,X
A435 B0 05   		BCS	BOUND5
A437 FE AD 09		INC	XSIGN,X
A43A 49 FF   		EOR	#$FF
A43C         	BOUND5
A43C 9D 40 0A		STA	XPOSH,X
A43F         	BOUND4
A43F 8A      		TXA
A440 18      		CLC
A441 69 31   		ADC	#RAMNUM
A443 AA      		TAX
A444 C6 6A   		DEC	TEMP
A446 10 E0   		BPL	BOUND3
A448 88      		DEY
A449 10 D7   		BPL	BOUND1		; NEXT STAR
             	;
             	;

             	;		CALCVH
             	;	CALCULATE V,H POS FOR ALL STARS/OBJ
A44B A5 D0   		LDA	DISFLG
A44D C9 02   		CMP	#$02
A44F B0 5C   		BCS	CALC14		; NOT FRONT OR BACK
             	;
A451 A6 79   		LDX	NSTARS		; X=INDEX OF STARS
A453         	CALCV1			;STAR LOOP
A453 A9 FF   		LDA	#$FF
A455 BC AD 09		LDY	XSIGN,X
A458 C4 D0   		CPY	DISFLG
A45A F0 4B   		BEQ	CALCV5
             	;
             	;	UPDATE VPOS
             	;
A45C BD 0F 0A		LDA	ZSIGN,X		; 2'S COMPLE ZOPS?
A45F D0 12   		BNE	CALCV8		; NO
             	;			2'S COMPLEMENT
A461 38      		SEC
A462 A9 00   		LDA	#$00
A464 FD 35 0B		SBC	ZPOSL,X
A467 85 6A   		STA	TEMP
A469 A9 00   		LDA	#$00
A46B FD A2 0A		SBC	ZPOSH,X
A46E 85 6B   		STA	TEMP1
A470 4C 7D A4		JMP	CALCV9
A473         	CALCV8
A473 BD 35 0B		LDA	ZPOSL,X
A476 85 6A   		STA	TEMP		; STORE IN TOP REG
A478 BD A2 0A		LDA	ZPOSH,X
A47B 85 6B   		STA	TEMP1
A47D         	CALCV9
A47D 20 21 AA		JSR	DIVIDE		; DIVIDE ZPOS BY XPOS
A480 20 1E B7		JSR	STVPOS		; STOE VPO
             	;
             	;			UPDATE HORIZ POS
             	;
             	;
A483 BD DE 09		LDA	YSIGN,X		; 2'S COMPLE YPOS ?
A486 D0 12   		BNE	CALCV3		; NO.
             	;		2'S COMPLEMENT
A488 38      		SEC
A489 A9 00   		LDA	#$00
A48B FD 04 0B		SBC	YPOSL,X
A48E 85 6A   		STA	TEMP		; STORE IN TOP(NUMERATOR)REG
A490 A9 00   		LDA	#$00
A492 FD 71 0A		SBC	YPOSL,X
A495 85 6B   		STA	TEMP1
A497 4A A4 A4		JMP	CALCV4
A49A         	CALCV3
A49A BD 04 0B		LDA	YPOSL,X		; SOTRE IN TOP REG
A49D 85 6A   		STA	TEMP
A49F BD 71 0A		LDA	YPOSK,X
A4A2 85 6B   		STA	TEMP1
A4A4         	CALCV4
A4A4 20 21 AA		JSR	DIVIDE		; DIVIDE YPOS BY XPOS
A4A7         	CALCV5
A4A7 20 FB B6		JSR	SHTPOS		;	STORE HPOS
             	;
A4AA CA      		DEX
A4AB 10 A6   		BPL	CALCV1		; NEXT STAR
             	;		ALL DONE
A4AD         	CALC14
             	;
             	;

A4AD 20 62 B1		JSR	CSERVE		; SERVICE GALACTIC CHART
             	;
             	;
             	;	SSERVE
             	;		SECTOR SCAN SERVE
A4B0 24 D0   		BIT	DISFL0
A4B2 50 31   		BVC	SSERV1
A4B4 A2 31   		LDX	#INSTB2-INSTAB		; LOAD SECTOR SCAN SHIP
A4B6 20 6F A7		JSR	LDINST
A4B9 2C 96 09		BIT	DAMAGE+4		; SECTOR SCAN DAMAGE
A4BC 70 27   		BVS	SSERV1
             	;
A4BE A6 79   		LDX	NSTARS
A4C0         	SSERV2
A4C0 BD 40 0A		LDA	XPOSH,X
A4C3 BC AD 09		LDY	XSIGN,X
A4C6 D0 02   		BNE	SSERV3
A4C8 49 FF   		EOR	#$FF
A4CA         	SSERV3
A4CA A8      		TAY
             	;
A4CB B9 E9 0D		LDA	PTAB,Y
A4CE 20 1E B7		JSR	STVPOS
A4D1 BD 71 0A		LDA	YPOSH,X
A4D4 BC DE 09		LDY	YSIGN,X
A4D7 D0 02   		BNE	SSERV4
A4D9 49 FF   		EOR	#$FF
A4DB         	SSERV4
A4DB A8      		TAY
             	;
A4DC B9 E9 0D		LDA	PTAB,Y
A4DF 20 FB B6		JSR	STHPOS
A4E2 CA      		DEX
A4E3 10 DB   		BPL	SSERV2
A4E5         	SSERV1
             	;
             	;

             	;		OBJCOL
             	;		SELECT OBJECT COLOR , GRAPHIC
A4E5 A2 05   		LDX	#OBLAST+1
A4E7         	OBJCL2		; OBJCT LOOP
A4E7 CA      		DEX
A4E8 10 03   		BPL	OBJCL1
A4EA 4C 79 A5		JMP	OBJC12
A4ED         	OBJCL1
A4ED A9 00   		LDA	#$00
A4EF 95 E4   		STA	GRAPH,X		; SET GRAPH PNTR TO NULL GRAPHIC
A4F1 9D EE 0C		STA	NUMBYT,X		; STORE 1 BYTE ONLY
A4F4 24 D0   		BIT	DISFLG		; GALACTIC CHART ?
A4F6 10 0B   		BPL	OBJCL3		; NO
A4F8 E0 03   		CPX	#$03		; OBJ 0,1,2 ?
A4FA 90 EB   		BCC	OBJCL2		; YES , NO DISPLAY
A4FC         	OBJCL4
A4FC AD 0A D2		LDA	RANDOM		; RANDOM COLOR
A4FF A0 F2   		LDY	#$F2		; SMALL SIZE
A501 30 2B   		BMI	OBJCL6		; JMP
A503         	     	OBJCL3
A503 D5 E9   		CMP	STFLAG,X		; OBJECT ON ?
A505 F0 E0   		BEQ	OBJCL2			; NO
A507 70 F3   		BVS	OBJCL4		; SECTOR SCAN
A509 BC 40 0A		LDY	XPOSH,X		; INTENSITY AND GRAPHIC SIZE
A50C 24 7B   		BIT	BASFLG		; STARBASE ?
A50E 50 1E   		BVC	OBJCL6		; NO
A510 E0 02   		CPX	#$02		; SBASE OBJECTS ?
A512 B0 16   		BCS OBJCL8		; NO
A514 AD 2C 0C		LDA	HPOS+2		; GANG OBJ 0,1,2 TOGETHER
A517 18      		CLC			; OBJ 2 IS REFERENCE
A518 7D DB BE		ADC	BHORTB,X	; HORIZ OFFSET , +8,-8
A51B 9D 2A 0C		STA	HPOS,X
A51E AD FB 0B		LDA	VPOS+2		; GANG VPOS
A521 18      		CLC
A522 69 04   		ADC	#4
A524 9D F9 0B		STA	VPOS,X
A527 AC 42 0A		LDY	XPOSH+2		; ALL USE OBJ2 POSIT.
A52A         	OBJCL8
A52A A5 76   		LDA	BINTIM		; MODULATE STARBASE COLOR
A52C 29 0F   		AND	#$0F
A25E         	OBJCL6
A52E 85 6B   		STA	TEMP1		; COLOR MODULATE
A530 98      		TYA			; XPOSH
A531 BC F9 0B		LDY	VPOS,X		; IN BOUNDS CHECK
A534 C0 CC   		CPY	#$CC		; IN BOUNDS ?
A536 B0 AF   		BCS	OBJCL2		; NO
A538 A4 D0   		LDY	DISFLG		; FRONT OR BACK ?
A53A F0 02   		BEQ	OBJCL7		; FRONT
A53C 49 FF   		EOR	#$FF		; ONES COMPLEMENT XPOSH
A53E         	OBJCL7
A53E C9 20   		CMP	#$20		; TOO FAR AWAY ?
A540 B0 A5   		BCS OBJCL2		; YES
A542 C9 10   		CMP	#$10		; SMALLEST SIZE ?
A544 90 02   		BCC	OBJCL5		; NO
A546 A9 0F   		LDA	#$0F		; SMALL SIZE
A548         	OBJCL5				; LD COLOR, GRAPHIC PNTRS
A548 85 AA   		STA TEMP		; TEMP SAVE XPOSH
A54A 1D 8C 0C		ORA GINDEX,X			; TYPE OF GRAPHIC
A54D 4A      		LSR	A		; ONLY 8 VALUES PER TYPE
A54E A8      		TAY
A54F B9 2F BE		LDA	GPOINT,Y		; OFFSET FROM PHGRAF, OR ZYGRAF
A552 95 E4   		STA	GRAPH,X		; HOLDS INDEX
A554 B9 7F BE		LDA	NBYTAB,Y
A557 9D EE 0C		STA	NUMBYT,X		; NUMBER OF BYTES TO SAVE
A55A 98      		TYA
A55B 4A      		LSR	A
A55C 4A      		LSR	A
A55D 4A      		LSR	A
A55E A8      		TAY			; GINDEX ONLY
A55F B9 D1 BF		LDA	COLTAB,Y		; CHROMA OF OBJ
A562 C0 08   		CPY	#$08		; BASE STAR ?
A564 D0 03   		BNE	OBJC11		; NO
A566 4D 0A D2		EOR	RANDOM		; RANDOM COLOR
A569         	OBJC11
A569 A4 6A   		LDY	TEMP		; DISTANCE FOR INTENSITY
A56B 59 DB BF		EOR	COLINT,Y	; INTENSITY
A56E 45 6B   		EOR	TEMP1		; COLOR MODULATE , IF ANY
A570 BC DF B8		LDY	CLINDX,X	; WHERE TO STORE
A573 99 EE 00		STA	COLRAM,Y	; COLOR UPDATED
A576 4C E7 A4		JMP	OBJCL2		; NEXT OBJ
A579         	OBJC12

             	;		STRBRT
             	;		STAR BRIGHTNESS INTENSITY NEW STAR CALC
             	;
A579 A0 AF   		LDY	#BRTBLU
A57B A6 81   		LDX	SPABAK
A5D7 A5 8B   		LDA	REDFLG
A57F F0 0C   		BEQ	STRBR2
A581 C6 8B   		DEC	REDFLG		; TIME OUT RED ALERT
A583 A0 4F   		LDY	#BRTRED
A585 29 20   		AND	#$20
A587 F0 04   		BEQ	STRBR2
A589 A2 42   		LDX	#DIMRED
A58B A0 60   		LDY	#DRKRED
A58D         	STRBR2
A58D 84 F4   		STY	COLRAM+6		; PF2
A58F 86 F6   		STX	COLRAM+8		; BAK
A591 A6 79   		LDX	NSTARS		; X=INDWX , INIT TO LAST STAR
A593         	STRBR1
A593 BD 40 0A		LDA	XPOSH,X		; INTENSITY DETERMINED BY XPOS
A596 A4 D0   		LDY	DISFLG		; FRONT OR BACK  ?
A598 C0 01   		CPY	#$01		; ALL BUT BACK VIEW WILL BRANCH
A59A D0 09   		BNE	STRBR5		; FRONT
A59C C9 F0   		CMP	#$F0		; STAR AT MINUS BOUNDS ?
A59E B0 03   		BCS	STRBR6
A5A0 20 64 B7		JSR	NEWSTR
A5A3         	STRBR6
A5A3 49 FF   		EOR	#$FF		; COMPLEMENT XPOS
A5A5         	STRBR5
A5A5 C9 10   		CMP	#$10		; USE DEFAULT ?
A5A7 90 02   		BCC	STRBR4		; NO
A5A9 A9 0F   		LDA	#$0F		; DEFAULT
A5AB         	STRBR4
A5AB 0A      		ASL	A
A5AC 29 1C   		AND	#$1C
A5AE 05 72   		ORA	TIMERX			; MULTIPLEX	WITH FRAME OUNT
A5B0 A8      		TAY				; FOR 8 APPARENT LEVELS OF BRIGHT
A5B1 B9 90 BA		LDY	BRTABL,Y		; WHICH PLAYFIELD
A5B4 85 6A   		STA	TEMP
A5B6 BD 2A 0C		LDA	HPOS,X
A5B9 20 03   		AND	#$03
A5BB A8      		TAY
A5BC B9 B0 BA		LDA	MASK,Y
A5BF 25 6A   		AND	TEMP
AC51 9D EE 0C		STA	STRBYT,X		; DATA TO STORE IN STOSTR
A5C4 CA      		DEX
A5C5 E0 05   		CPX	#OBJNUM			; ALL DONE WITH STARS ?
A5C7 B0 CA   		BCS	STRBR1			; NEXT STAR
             		;		ALL DONE

             	;
             	;	END STAR/OBJECTS MOVE ROUTINES
             	;
             	;
             	;
             	;	GAME ON ROUTINES
             	;		PLAYER INTERFACE SECTION AND SERVICE SECTION, HIT DETECT
             	;
A5C9 24 64   		BIT	ATRACT		; GAME OVER LOCKOUT PLAYER
A5CB 50 03   		BVC	MAIN4		; YES
A5CD 4C 9B A6		JMP	MAIN3
A5D0         	MAIN4
             	;
A5D0 20 FE AF		JSR	KEYSRV		; SERVICE JEYBOARD
             	;		JOYSTK
             	;		JOYSTICK EVALUATION ROUTINE
A5D3 AD 00 D3		LDA	PROTA
A5D6 A8      		TAY		; STORE TEMP
A5D7 29 03   		AND	#$03		; VERT ONLY
A5D9 AA      		TAX
A5DA BD F5 BA		LDA	JOYTAB,X		; CODE FOR VERT
A5DD 85 C9   		STA	VERJOY
A5DF 98      		TYA		; PORT A AGAIN
A5E0 4A      		LSR	A
A5E1 4A      		LSR	A
A5E2 29 03   		AND	#$03
A5E4 AA      		TAX			; HORIZ ONLY
A5E5 BD F5 BA		LDA	JOYTAB,X		; CODE FOR HORIZ
A5E8 85 C8   		STA	HORJOY

A5EA 20 3D AF		JSR	HITZYL		; HIT ZYLON
A5ED 20 29 AE		JSR	PHOTON		; SERVICE TRIGGERS
             	;		ASERVER
             	;		ATTACK CPMPUTER SERVICE
A5F0 2C 95 09		BIT	DAMAGE+3
A5F3 70 40   		BVS	ASERV2
A5F5 A5 7E   		LDA	ATENER		; ATTACK ON ?
A5F7 F0 3C   		BEQ	ASERV2		; NO
A5F9 A5 D0   		LDA	DISFLG
A5FB D0 03   		BNE	ASERV1
A5FD 20 BF A7		JSR	UPINST
A600         	ASERV1
             	;
             	;		AUTO TARGET SELECTOR
             	;
A600 AE 5C 09		LDX	DCSTOR
A603 A5 BF   		LDA	ATTARG
A605 30 05   		BMI	ASERV4
A607 AA      		TAX
A608 09 80   		ORA	#$80
A60A 85 BF   		STA	ATTARG
A60C         	ASERV4
A60C B5 E9   		LDA	STFLAG,X
A60E D0 0B   		BNE	ASERV3
A610 8A      		TXA
A611 49 01   		EOX	#$01
A613 AA      		TAX
A614 B5 E9   		LDA	STFLAG,X
A616 D0 03   		BNE	ASERV3
A618 AE 5C 09		LDX	DCSTOR
A61B         	ASERV3
A61B 8E 5C 09		STX	DCSTOR
             	;
             	;		COMPUTER AUTO TRACKING
A61E A5 7C   		LDA	TRKFLG
A620 F0 13   		BEQ	ASERV2
A622 A5 D0   		LDA	DISFLG
A624 C9 02   		CMP	#$02		; FRONT OR BAK ?
A626 B0 0D   		BCS	ASERV2		; NO
A628 49 01   		EOR	#$01		; WHICH DISFLG
A62A DD AD 09		CMP	XSIGN,X		; OBJ IN SIGHT ?
A62D F0 06   		BEQ	ASERV2		; YES
A62F AA      		TAX
A630 BD CF BE		LDA	TRKTAB,X		; WHICH KEY FOR SWITCHING DISPLAY
A633 85 CA   		STA	THEKEY		; SWITCH DISPLAY
A635         	ASERV2
             	;

A635 20 E6 AC		JSR	BSERVE		; SERVICE STARBASE
A638 20 79 AA		JSR	THINK		; SERVICE ZYLON BRAIL
             	;		HITSHP
             	;		RAIDER HIT PHOTON HIT DETECT
A63B A5 7B   		LDA	BASFLG		; STARBASE ?
A63D D0 5C   		BNE	HITSH1		; YES
A63F A5 EB   		LDA	STFLAG+2
A641 F0 58   		BEQ	HITSH1
A643 AC 42 0A		LDY	XPOSH+2
A646 C8      		INY
A647 C0 02   		CPY	#$02
A649 B0 50   		BCS	HITSH1
A64B AC 73 0A		LDY	YPOSH+2
A64E C8      		INY
A64F C0 02   		CPY	#$02
A651 B0 48   		BCS	HITSH1
A653 AC A4 0A		LDY	ZPOSH+2
A656 C8      		INY
A657 C0 02   		CPY	#$02
A659 B0 40   		BCS	HITSH1
             		;			A HIT !!
A65B 20 E1 AE		JSR	DAMCTL
A65E A0 02   		LDY	#$02
A660 20 6B AC		JSR	EXPLOS
A663 A2 7F   		LDX	#$7F
A665 A5 81   		LDA	SPABAK		; DEAD ?
A667 D0 1E   		BNE	HITSH2		; NO
A669 A2 0A   		LDX	#$0A		; FRONT
A66B 20 45 B0		JSR	KEYS15
A66E A0 23   		LDY	#SENDST-SENTAB
A670 A2 08   		LDX	#$08		; DESTROYED
A672 20 0A B1		JSR	CRATE
A675 A2 5F   		LDX	#DISPL3-DISPLY
A677 A0 80   		LDY	#$80
A679 A9 08   		LDA	#$08
A67B 20 F1 AD		JSR	LDISP
A67E 20 0D AE		JSR	CLRMAP
A681 A2 40   		LDX	#$40		; ITS ALL OVER
A683 86 E3   		STX	BIGEXP
A685 A2 FF   		LDX	#$FF		; HIT ME DEAD
A687         	HITSH2
A687 86 8A   		STX	HITME
A689 86 8A   		LDA	#$00
A68B 85 EB   		STA	STFLAG+2
A68D A9 02   		LDA	#$02
A68F 85 BE   		STA	PHEXWT
             	;
A691 A2 01   		LDX	#$01
A693 20 6F B8		JSR	PANDS6
A696 A2 0A   		LDX	#NOITB1-NOISTB
A698 20 A8 AE		JSR	NOISE
A69B         	HITSH1

             	;		END GAME ON ROUTINES

A69B         	MAIN3
             	;
             	;
              	;		CONTINOUS RUNNING ROUTINES
              	;		CONSRV
              	;		SERVICE CONSOL ROUTINE
A69B A4 63   		LDY	RESET
A69D AD 1F D0		LDA	CONSOL
A6A0 49 FF   		EOR	#$FF		; POSITIVE LOGIC
A6A2 29 03   		AND	#$03
A6A4 85 63   		STA	RESET
A6A6 F0 1A   		BEQ	CONSR2
A6A8 88       		DEY
A6A9 10 17   		BPL	CONSR2
A6Ab 85 66   		STA	TIMOUT		; RESET TIMOUT
A6AD C9 02   		CMP	#$02
A6AF B0 06   		BCS	CONSR3		; GAME SELECT
A6B1 A9 00   		LDA	#$00
A6B3 A8      		TAY
A6B4 4C 5E A1		JMP	INIT1		; GAME START
A6B7         	CONSR3
A6B7 E6 62   		INC	MISDIF
A6B9 A5 62   		LDA	MISDIF
A6BB 29 03   		AND	#$03
A6BD 85 62   		STA	MISDIF
A6BF 4C 5A A1		JMP	INIT3
AC62         	CONSR2
             	;
             	;

A6C2 20 04 B8		JSR	PASDIN		; SERVICE PANEL DISPLAY
A6C5 20 9B A8		JSR	HSERVE		; SERVICE HYPERWARP JUMP
A6C8 20 16 B2		JSR	MSERVE		; SERVICE MESSAGE
A6CB 20 E4 B4		JSR	TIMERS		; EVALUATE ALL TIMERS , TIMEOUTS, ETC.
             	;		END CONTINOUS RUNNING ROUTINES
             	;
             	;
             	;
A6CE 4C F3 A1		JMP	MAIN		; END VBLANK ROUTINE, WAIT FOR NEW VBLANK
             	;
             	;
             	;
             	;
             	;		NMI INTERRUPT SERVICE SECTION
             	;
             	;
A6D1         	VBNMI
A6D1 A9 FF   		LDA	#$FF
A6D3 85 67   		STA	PROGST			; SET PROGST VBLANK NMI FLAG
A6D5 A9 E0   		LDA	#ALPHA/256
A6D7 8D 09 D4		STA	CHBASE		; USE STANDARD ALPHA CHARACTERS
A6DA A6 F6   		LDX	COLRAM+8		; BAK
A6DC AD 0A D2		LDA	RANDOM
A6DF 24 8A   		BIT	HTIME
A6E1 50 07   		BVC	VBLNK4
A6E3 30 04   		BMI	VBLNK1
A6E5 29 72   		AND	#$72
A6E7 09 40   		ORA	#$40
A6E9         	VBLNK1
A6E9 AA      		TAX
A6EA         	VBNLK4
A6EA A5 D0   		LDA	DISFLG
A6EC C9 03   		CMP	#$03
A6EE 90 02   		BCC	VBLNK2
A6F0 A2 A0   		LDX	#DBLUE
A6F2         	VBLNK2
A6F2 86 F6   		STX	COLRAM+8		; BAK
             	;
A6F4 A2 08   		LDX	#$08
A6F6         	VBLNK3
A6F6 B5 EE   		LDA	COLRAM+0,X
A6F8 9D 12 D0		STA	COLPM0,X
A6FB CA      		DEX
A6FC 10 F8   		BPL	VBLNK3
             	;
             	;
A6FE 8D 1E D0		STA	HITCLR		; RESET HITS
             	;
A701 20 AB B2		JSR	AUDIO		; SERVICE AUDIO
             	;
A704 E6 77   		INC	BINNMI		; ATRACT MODE STUFF
A706 D0 0D   		BNE	VBLNK5
A708 A5 66   		LDA	TIMOUT
A70A 30 09   		BMI	VBLNK5
A70C E6 66   		INC	TIMOUT
A70E 10 05   		BPL	VBLNK5
A710 10 05   		BPL	VBLNK5
A712 A4 5C A1		JMP	INIT4
A715         		VBLNK5
             	;
             	;
A715 4C 4B A7		JMP	POPALL
             	;
A718         	DISNMI
A718 48      		PHA		; PUSH ALL REGISTERS FOR OP SYSTEM
A719 8A      		TXA
A71A 48      		PHA
A71B 98      		TYA
A71C 48      		PHA
A71D A9 E0   		LDA	#ALPHA/256
A71F AC 0B D4		LDY	VCOUNT
A722 C0 60   		CPY	#$60
A724 F0 02   		BEQ	DISNMI
A726 A9 A0   		LDA	#CGRAPH/256
A728         	DISNM1
A728 8D 09 D4		STA	CHBASE		; USE FUTURE TYPE CHARACTER SET
             	;
A72B A2 04   		LDX	#$04
A72D 8D 0A D4		STA	WSYNC
A730         	DISNM2
A730 B5 F7   		LDA	COLRAM+9,X
A732 9D 16 D0		STA	COLPF0,X
A735 CA      		DEX
A736 10 FB   		BPL	DISNM2
             	;
             	;		READ HITS
A738 AD 08 D0		LDA	M0PL
A73B 0D 09 D0		ORA	M1PL
A73E 0D 0A D0		ORA	M2PL
A741 0D 0B D0		ORA	M3PL
A744 85 83   		STA	PHITS+1		; PHOTON 3 STORED
A746 AD 0F D0		LDA	P3PL
A749 85 82   		STA	PHITS+0		; PHOTON 2 STORED
A748         	POPALL
A748 68      		PLA
A74C A8      		TAY
A74D 68      		PLA
A74E AA      		TAX
A74F 68      		PLA
             	;
             	;			END POP
             	;
A759 40      		RTI
             	;
             	;
             	;
             	;
             	;
             	;		IRQ INTERRUPT SERVICE SECTION
             	;
A751		IRQVEC
             	;		PUSH ACCUM REGISTERS
A751 48      		PHA
             	;			END PUSH
A752 A9 00   		LDA	#$00
A754 8D 0E D2		STA	IRQEN		; RESET IRQ'S
A757 A9 40   		LDA	#IRQMSK
A759 8D 0E D2		STA	IRQEN
A75C AD 09 D2		LDA	KBCODE
A75F 09 C0   		ORA	#$C0
A761 85 CA   		STA	THEKEY
A763 68      		PLA
A764 40      		RTI
             	;
             	;			END IRQ INTERRUPT SECTION
             	;
             	;
             	;
             	;			SUBROUTINES,
             	;
             	;
             	;
A765         	LDINS6		; LOAD UP THE LINE
A765 99 A4 00		STA	NUMPTS,Y
A768 E8      		INX
A769 88      		DEY
A76A 10 0E   		BPL	LDINS4
A76C 20 82 A7		JSR	DRAWER
A76F         	LDINST
             	;		LOAD INSET	RESERVE BYTE=$FE
             		;	X= INITIAL START OF PNTR IN INSTAB
A76F A9 05   		LDA	#$05
A771 85 A2   		STA	TARPTR		; DEFINE TARGET POINTER
A773 2C 95 09		BIT	DAMAGE+3		; COMPUTER
A776 70 09   		BVS	LDINS2
A778         	LDINS1
A778 A0 02   		LDY	#$02
A77A         	LDINS4
A77A BD F9 BA		LDA	INSTAB,X
A77D C9 FE   		CMP	#$FE		; ALL DONE
A77F D0 E4   		BNE	LDINS6		; NO
A781         	LDINS2
A781 60      		RTS
             	;
             	;
A782         	DRAWER			; DRAW THE LINE
A782 A9 55   		LDA	#$55
A784         	DRAWR3		; ENTRY POINT FROM UPINST  ************************
A784 85 6B   		STA	TEMP1
A786 A5 A4   		LDA	NUMPTS
A788 85 6E   		STA	TEMP4
A78A 29 7F   		AND	#$7F
A78C 85 A4   		STA	NUMPTS
A78E         	DRAWR1
A78E A4 A5   		LDY	VDRAW
A790 B9 00 08		LDA	VCONL,Y
A793 85 68   		STA	PNTR
A795 B9 64 08		LDA	VCONH,Y
A798 85 69   		STA	PNTR+1
A79A A5 A6   		LDA	HDRAW
A79C 4A      		LSR	A
A79D 4A      		LSR	A
A79E 85 6A   		STA	TEMP
A7A0 A5 A6   		LDA	HDRAW
A7A2 29 03   		AND	#$03
A7A4 A8      		TAY
A7A5 B9 B0 BA		LDA	MASK,Y
A7A8 25 6B   		AND	TEMP1
A7AA A4 6A   		LDY	TEMP
A7AC 11 68   		ORA	(PNTR),Y
A7AE 91 68   		STA	(PNTR),Y
A7B0 24 6E   		BIT	TEMP4
A7B2 10 04   		BPL	DRAWR4
A7B4 E6 A5   		INC	VDRAW
A7B6 D0 02   		BNE	DRAWR5		; JUMP, VDRAW CANNOT CROSS 0 !!
A7B8         	DRAWR4
A7B8 E6 A6   		INC	HDRAW
A7BA         	DRAWR5
A7BA C6 A4   		DEC	NUMPTS		; POINTS ALL DRAWN ?
A7BC D0 D0   		BNE	DRAWR1
A7BE         	DRAWR2
A7BE 60      		RTS
             	;
             	;
             	;
             	;
A7BF         UPINST
             	;		UPDATE  INSET
             	;
             	;		FIRE CONTROL
A7BF AE 5C 09		LDX	DCSTOR		; WHICH OBJECT
A7C2 A4 A2   		LDY	TARPTR
A7C4 C0 05   		CPY	#$05
A7C6 B0 24   		BCS	UPINST2
             	;		LD TARGET DISPLAY
A7C8 A5 A0   		LDA	HTARGT
A7CA 85 A6   		STA	HDRAW
A7CC B9 6E BF		LDA	ZYTARG,Y
A7CF         	UPINS8
A7CF 0A      		ASL	A
A7D0 85 C6   		STA	TEMP2
A7D2 90 0D   		BCC	UPINST9
A7D4 A9 81   		LDA	#$81
A7D6 85 A4   		STA	NUMPTS
A7D8 A5 A1   		LDA	VTARGT
A7DA 85 A5   		STA	VDRAW
A7DC A9 AA   		LDA	#$AA
A7DE 20 84 A7		JSR	DRAWR3
A7E1         	UPINS9
A7E1 E6 A6   		INC	HDRAW
A7E3 A5 6C   		LDA	TEMP2
A7E5 D0 E8   		BNE	UPINS8
A7E7 E6 A1   		INC	VTARGT
A7E9         	UPIN10
A7E9 E6 A2   		INC	TARPTR
A7EB 60      		RTS
A7EC         	UPINS2
A7EC C0 0A   		CPY	#$0A
A7EE 90 F9   		BCC	UPIN10
A7F0 B5 E9   		LDA	STFLAG,X
A7F2 F0 3C   		BEQ	UPINS3
A7F4 BD 71 0A		LDA	YPOSH,X
A7F7 BC DE 09		LDY	YSIGN,X
A7FA F0 08   		BEQ	UPINS4
A7FC C9 0C   		CMP	#$0C
A7FE 90 0A   		BCC	UPINS5
A804         	UPINS4
A804 C9 F5   		CMP	#$F5
A806 B0 02   		BCS	UPINS5
A808 A9 F5   		LDA	#$F5
A80A         	UPINS5
A80A 18      		CLC
A80B 69 83   		ADC	#131
A80D 85 A0   		STA	HTRGT
A80F BD A2 0A		LDA	ZPOSH,X
A812 49 FF   		EOR	#$FF
A814 BC 0F 0A		LDA	ZSIGN,X
A817 D0 08   		BNE	UPINS6
A819 C9 05   		CMP	#$05
A81B 90 0A   		BCC	UPINS7
A81D A9 04   		LDA	#$04
A81F 10 06   		BPL	UPINS7		; JUMP
A821         	UPINS6
A821 C9 FA   		CMP	#$FA
A823 B0 02   		BCS	UPINS7
A825 A9 FA   		LDA	#$FA
A827         	UPINS7
A827 18      		CLC
A828 69 4D   		ADC	#77
A82A 85 A1   		STA	VTARGT
A82C A9 00   		LDA	#$00
A82E 85 A2   		STA	TARPTR
A830         	UPINS3
             	;		CLEAR INSET
A830 A9 36   		LDA	#INSET
A832 85 68   		STA	PNTR
A834 A9 1B   		LDA	#INSET/256
A836 85 69   		STA	PNTR+1
A838 A2 0E   		LDX	#14
A83A         	UPIN12
A38A A0 06   		LDY	#$06
A83C         	UPIN13
A83C B1 68   		LDA	(PNTR),Y
A83E 29 55   		AND	#$55
A840 91 68   		STA	(PNTR),Y
A842 88      		DEY
A843 10 F7   		BPL	UPIN13
A845 18      		CLC
A846 A5 68   		LDA	PNTR
A848 69 28   		ADC	#40
A84A 85 68   		STA	PNTR
A84C 90 02   		BCC	UPIN14
A84E E6 69   		INC	PNTR+1
A850         	UPIN14
A850 CA      		DEX
A851 1 E7   		BPL	UPIN12
             	;		DONE CLEAR INSET
A853 AE 5C 09		LDX	DCSTOR
A856 C8      		INY		; Y=0
A857 A5 88   		LDA	LOKWAT
A859 F0 04   		BEQ	UPIN11
A85B C6 88   		DEC	LOKWAT
A85D D0 39   		BNE	UPINS1
A85F         	UPIN11
A85F A5 A0   		LDA	HTARGT
A861 C9 81   		CMP	#129
A863 90 33   		BCC	UPINS1
A865 C9 85   		CMP	#133
A867 B0 2F   		BCS	UPINS1
A869 A9 AA   		LDA	#$AA
A86B 8D FE 1B		STA	ICON2
A86E 8D 04 1C		STA	ICON2+6
A871 A5 A1   		LDA	VTARGT
A873 C9 4B   		CMP	#75
A875 90 21   		BCC	UPINS1
A877 C9 4F   		CMP	#79
A879 B0 1D   		BCS	UPINS1
A87B A9 AA   		LDA	#$AA
A87D 8D 9E 1C		STA	ICON2+160
A880 8D A4 1C		STA	ICON2+166
A883 BD 40 0A		LDA	XPOSH,X
A886 C9 0C   		CMP	#$0C
A888 B0 0E   		BCS	UPINS1
A88A A0 A0   		LDY	#$A0
A88C 8C 40 1D		STY	ICON1
A88F 8C 68 1D		STY	ICON1+40
A892 8C 42 1D		STY	ICON1+2
A895 8C 6A 1D		STY	ICON1+42
A898         	UPINS1
A989 84 A3   		STY	LOKFLG
A89A 60      		RTS
             	;
             	;
             	;
             	;
             	;
             	;
A89B         	HSERVE
             	;		HYPERWARP SERVICE ROUTINE
A89B A4 C0   		LDY	HFLAG		; HWAPR ?
A89D F0 61   		BEQ	HSERV4		; NO
A89F A5 70   		LDA	SEEPD
A8A1 C9 FE   		CMP	#$FE		; UP TO SPEED ?
A8A3 B0 5C   		BCS	HSERV5		; YES
A8A5 C9 80   		CMP	#$80		; DO LINES ?
A8A7 90 03   		BCC	HSERV6		; NO
A8A9 29 B4 A9		JSR	HLINES
A8AC         	HSERV6
             	;		STEERING STUFF
A8AC 90 03   		LDA	#$03
A8AE 8D 5C 09		STA	DCSTOR
A8B1 A9 90   		LDA	#$90
A8B3 8D 8F 0C		STA	GINDEX+3
A8B6 85 EC   		STA	STFLAG+3
A8B8 A9 1F   		LDA	#$1F
A8BA 8D 43 0A		STA	XPOSH+3
A8BD 38      		SEC
A8BE AD FC 0B		LDA	VPOS+3
A8C1 E9 77   		SBC	#VOBCEN-3
A8C3 18      		CLC
A8C4 65 C5   		ADC	VSTEER
A8C6 29 7F   		AND	#$7F
A8C8 85 8E   		STA	HYVPOS
A8CA 38      		SEC
A8CB AD 2D 0C		LDA	HPOS+3
A8CE E9 7D   		SBC	#HOBCEN
A8D0 18      		CLC
A8D1 65 C4   		ADC	HSTEER
A8D3 29 7F   		AND	#$7F
A8D5 85 8F   		STA	HYHPOS
A8D7 A5 62   		LDA	MISDIF
A8D9 F0 11   		BEQ	HSERV7
A8DB AD 0A D2		LDA	RANDOM
A8DE A4 D0   		LDY	DISFLG
A8E0 F0 06   		BEQ	HSERV9
A8E2 8D 2D 0C		STA	HPOS+3
A8E5 8D FC 0B		STA	VPOS+3
A8E8         	HSERV9
A8C8 C9 10   		CMP	#$10
A8EA B0 14   		BCS	HSERV4
A8EC         	HSERV7
A8EC AD 0A D2		LDA	RANDOM
A8EF 09 10   		ORA	#$10
A8F1 25 C6   		AND	STERMK
A8F3 8D 9A 0B		STA	YINCRE+3
A8F6 AD 0A D2		LDA	RANDOM
A8F9 09 10   		ORA	#$10
A8FB 25 C6   		AND	STERMK
A8FD 8D CB 0B		STA	ZINCRE+3
A900         	HSERV4
A900 60      		RTS
A901         	HSERV5
A901 98      		TYA		; IN JUMP ?
A902 30 11   		BMI	HSERV8		; YES
             	;		BEGIN JUMP
A904 A9 FF   		LDA	#$FF
A906 85 C0   		STA	HFLAG
A908 A2 00   		LDX	#CH4TB1-CH4TAB
A90A 20 A6 B3		JSR	NOTINT
A90D 20 A7 B1		JSR	CSERV8		; JUMP ENERGY
A910 A0 1B   		LDY	#SENHSP-SENTAB
A912 4C 8D A9		JMP	HABOR1
A915         	HSERV8		; IN JUMP
A915 C6 91   		DEC	HYPENG		; ALL DONE ?
A917 F0 05   		BEQ	HSER10		; YES
A919 A2 02   		LDX	#$02		; DEC ENERGY
A91B 4C 6F B8		JMP	PANDS6
A91E         	HSER10
             	;		HWARP COMPLETE
A91E A0 19   		LDY	#SENHWC-SENTAB
A920 20 87 A9		JSR	HABOR2
A923 A5 8F   		LDA	HYHPOS
A925 85 8D   		STA	GHPOS
A927 A5 8E   		LDA	HYVPOS
A929 85 8C   		STA	GVPOS
A92B 4A      		LSR	A
A92C 29 07   		AND	#$07
A92E AA      		TAX
A92F BD B3 BF		LDA	JMASK,X
A932 85 C7   		STA	JMPMSK
A934 A4 92   		LDY	HYPGAD
A936 84 90   		STY	GUADRT
A938 A9 00   		LDA	#$00
A93A 85 7B   		STA	BASFLG
A93C BE C9 08		LDX	CHTRAM,Y
A93F 10 2E   		BPL	HSERV2
A941 A9 FF   		LDA	#$FF		; STARBASE STUFF
A943 85 7B   		STA	BASFLG
A945 A0 00   		LDY	#$00
A947         	HSERV3
A947 A9 00   		LDA	#$00
A949 99 68 0B		STA	XINCRE+2,Y
A94C A9 01   		LDA	#$01
A94E 99 AF 09		STA	XSIGN+2,Y
A951 AD 0A D2		LDA	RANDOM
A954 25 C7   		AND	JMPMSK
A956 99 42 0A		STA	XPOSH+2,Y
A959 98      		TYA
A95A 18      		CLC
A95B 69 31   		ADC	#RAMNUM
A95D A8      		TAY
A95E C9 93   		CMP	#RAMNUM*3
A960 90 E5   		BCC	HSERV3
A962 AD 42 0A		LDA	XPOSH+2
A965 09 71   		ORA	#$71
A967 8D 42 0A		STA	XPOSH+2
A96A A2 02   		LDX	#$02
A96C 4C BE B7		JMP	NEWST4
A96F         	HSERV2
A96F F0 0E   		BEQ	HSERV1
A971 A9 FF   		LDA	#$FF		; RED ALERT
A973 85 8B   		STA	REDFLG
A975 A2 06   		LDX	#CH4TB2-CH4TAB
A977 20 A6 B3		JSR	NOTINT
A97A A0 75   		LDY	#SENRED-SENTAB
A97C 20 23 B2		JSR	LDMESS
A97F         	HSERV1
A97F 60      		RTS
             	;
             	;
             	;
             	;
A980         	HABORT
             	;	HYPERWARP ABORT ROUTINE
A980 A2 01   		LDX	#$01
A982 20 6F B8		JSR	PANDS6
A985 A0 17   		LDY	#SENHWA-SENTAB		; ABORT
A987         	HABOR2		; ENTRY POINT HWARP COMPLETE  ***********************
A987 A9 00   		LDA	#$00
A989 85 71   		STA	WARP
A98B 85 C0   		STA	HFLAG
A98D         	HABOR1		; ENTRY POINT BEGIN JUMP  **************************
A98D A9 10   		LDA	#STLAST
A98F 85 79   		STA	NSTARS
A991 A9 00   		LDA	#$00
A993 85 C1   		STA	HISPED
A995 85 73   		STA	ETIMER		; KEEP PROGRAM FROM GOING SOUTH
A997 85 8A   		STA	HITME		; CLEAR THE OTHER EXPLOS BUG
A999 8D 8F 0C		STA	GINDEX+3
A99C 85 80   		STA	WPENER
A99E C0 17   		CPY	#SENHWA-SENTAB
A9A0 F0 04   		BEQ	HABOR3
A9A2 85 E9   		STA	STFLAG+0
A9A4 85 EA   		STA	STFLAG+1
A9A6         	HABOR3
A9A6 85 EB   		STA	STFLAG+2
A9A8 85 EC   		STA	STFLAG+3
A9AA 85 ED   		STA	STFLAG+4
A9AC 85 75   		STA	BSEQTM
A9AE 8D 5C 09		STA	DCSTOR
A9B1 4C 23 B2		JMP	LDMESS
             	;
             	;
             	;
             	;
A9B4         	HLINES
             	;		DRW HWARP LINES
A9B4 C6 C2   		DEC	HTIMER
A9B6 10 68   		BPL	HLINE1
A9B8 A9 10   		LDA	#$01
A9BA 85 C1   		STA	HISPED
A9BC A9 30   		LDA	#RMLAST		; HWARP STARS ON
A9BE 85 79   		STA	NSTARS
A9C0 A9 03   		LDA	#$03
A9C2 85 C2   		STA	HTIMER
             	;			RESET LINES
A9C4 A6 C3   		LDX	HPNTR
A9C6         	HLINE2
A9C6 A9 12   		LDA	#$12		; XINIT
A9C8 85 69   		STA	PNTR+1
A9CA AD 0A D2		LDA	RANDOM		; INIT Y,Z
A9CD 29 03   		AND	#$03
A9CF A8      		TAY
A9D0 B9 3A BB		LDA	YINIT,Y
A9D3 9D 71 0A		STA	YPOSH,X
A9D6 B9 3E BB		LDA	ZINIT,Y
A9D9 9D A2 0A		STA	ZPOSH,X
A9DC 20 BE B7		JSR	NEWST4		; WHICH QUADRANT
A9DF 8A      		TXA
A9E0 A8      		TAY			; X GOES TO Y
A9E1 A9 05   		LDA	#$05
A9E3 85 6E   		STA	TEMP4
A9E5         	HLINE4
             	;
A9E5 18      		CLC
A9E6 A5 68   		LDA	PNTR
A9E8 69 50   		ADC	#$50		; XINCRE
A9EA 85 68   		STA	PNTR
A9EC 9D D3 0A		STA	XPOSL,X
A9EF A5 69   		LDA	PNTR+1
A9F1 69 00   		ADC	#$00
A9F3 85 69   		STA	PNTR+1
A9F5 9D 40 0A		STA	XPOSH,X
A9F8 A9 00   		LDA	#$00
A9FA 9D 66 0B		STA	XINCRE,X
A9FD 9D 97 0B		STA	YINCRE,X
AA00 9D C8 0B		STA	ZINCRE,X
             	;
AA03 A9 01   		LDA	#$01
AA05 9D AD 09		STA	XSIGN,X		; AND THAT FIXES THAT
AA08 A9 63   		LDA	#$99		; OFF-SCREEN
AA0A 9D F9 0B		STA	VPOS,X
AA0D 9D 2A 0C		STA	HPOS,X
AA10 20 C1 AC		JSR	EXHLP1		; DEFINE Y,Z
AA13 CA      		DEX
AA14 E0 11   		CPX	#STLAST+1
AA16 B0 02   		BCS	HLINE3
AA18 A2 30   		LDX	#RMLAST
AA1A         	HLINE3
AA1A C6 6E   		DEC	TEMP4
AA1C 10 C7   		BPL	HLINE4
AA1E 86 C3   		STX	HPNTR
AA20         	HLINE1
AA20 60      		RTS
             		;
             	;
             	;
             	;
AA21         	DIVIDE
             	;	A = (TOP/BOTTOM)X80
             	;
AA21 A9 00   		LDA	#$00		;CLEAR THE RESULT
AA23 85 6D   		STA	TEMP3
AA25 A9 07   		LDA	#$07		; NUMBER OF SHIFTS
AA27 85 6E   		STA	TEMP4
             	;			SHIFT 0 INTO THE MSBIT
AA29 46 6B   		LSR	TEMP1		; TOP NUMBER
AA2B 66 6A   		ROR	TEMP
AA2D A5 D0   		LDA	DISFLG		; FRONT OR BACK  ?
2A2F D0 0F   		BNE	DIVID1		; BACK
AA31 BD 40 0A		LDA	XPOSH,X		; BOTTOM NUMBER
AA34 4A      		LSR	A
AA35 85 69   		STA	PNTR+1
AA37 BD D3 0A		LDA	XPOSL,X
AA3A 6A      		ROR	A
AA3B 85 68   		STA	PNTR
AA3D 4C 52 AA		JMP	DIVID2
AA40         	DIVID1
AA40 38      		SEC
AA41 A9 00   		LDA	#$00
AA43 FD D3 0A		SBC	XPOSL,X
AA46 85 68   		STA	PNTR
AA48 A9 00   		LDA	#$00
AA4A FD 40 0A		SBC	XPOSH,X
AA4D A4      		LSR	A
AA4E 85 69   		STA	PNTR+1
AA50 66 68   		ROR	PNTR
             	;
AA52         	DIVID2
AA52 06 6D   		ASL	TEMP3		; SHIFT RESULT
AA54 38      		SEC	; SUBTRACT BOTTOM FROM TOP
AA55 A5 6A   		LDA	TEMP
AA57 E5 68   		SBC	PNTR
AA59 A8      		TAY
AA5A A5 6B   		LDA	TEMP1
AA5C E5 69   		SBC	PNTR+1
AA5E 90 06   		BCC	DIVID3		; BOTTOM GREATER THAN TOP
             	;		TOP LARGER
AA60 85 6B   		STA	TEMP1		; STORE REMAINDER
AA62 84 6A   		STY	TEMP
AA64 E6 6D   		INC	TEMP3		; ADD 1 TO RESULT
AA66         	DIVID3
AA66 06 6A   		ASL	TEMP		; SHIFT TOP
AA68 26 6B   		ROL	TEMP1
AA6A 90 03   		BCC	DIVID4
             	;		IF TOP IS GREATER THN BOTTOM THEN OVERFLOW
AA6C A9 FF   		LDA	#$FF		; MAX VALUE TO RESULT
AA6E 60      		RTS
AA6F         	DIDIV4
AA6F C6 6E   		DEC	TEMP4		; NEXT BIT
AA71 10 DF   		BPL	DIVID2
AA73 A4 6D   		LDY	TEMP3		; RESULT IN Y
AA75 B9 E9 0D		LDA	PTAB,Y		; MULTIPLY BY 80  (PTAB)
AA78         	DIVID5		; ENTRY POINT FROM THINK  ******************
AA78 60      		RTS
             	;
             	;
             	;
             	;
AA79         	THINK
             	;		COMPUTER ATTACK SUBROUTINE
AA79 A5 C0   		LDA	HFLAG
AA7B 05 7B   		ORA	BASFLG
AA7D D0 F9   		BNE	DIVID5		; BRANCH TO RTS
             	;		CRUISER PHOTON CONVERGENCE
AA7F A5 86   		LDA	LOKLOC
AA81 F0 30   		BEQ	THIN38
AA83 A6 89   		LDX	LOKTAR
AA85 38      		SEC
AA86 BD F9 0B		LDA	VPOS,X
AA89 ED FC 0B		SBC	VPOS+3
AA8C 90 02   		BCC	THIN37
AA8E A9 00   		LDA	#$00
AA90         	THIN37
AA90 20 CA AE		JSR	POHELP
AA93 8D CB 0B		STA	ZINCRE+3
AA96 8D CC 0B		STA	ZINCRE+4
AA99 38      		SEC
AA9A AD 2D 0C		LDA	HPOS+3
AA9D FD 2A 0C		SBC	HPOS,X
AAA0 20 CA AE		JSR	POHELP
AAA3 8D 9A 0B		STA	YINCRE+3
AAA6 38      		SEC
AAA7 AD 2E 0C		LDA	HPOS+4
AAAA FD 2A 0C		SBC	HPOS,X
AAAD 20 CA AE		JSR	POHELP
AAB0 8D 9B 0B		STA	YINCRE+4
             	;
AAB3         	THIN38
             	;
             	;		HELPER FOR THINK
AAB3 A2 03   		LDX	#$03
AAB5         	THIN39
AAB5 D6 BA   		DEC	ROTTIM,X
AAB7 10 27   		BPL	THIN44
AAB9 8A      		TXA
AABA 4A      		LSR	A
AABB AB      		TAY
AABC B9 C8 00		LDA	HORJOY,Y
AABF A4 D0   		LDY	DISFLG
AAC1 F0 05   		BEQ	THIN40
AAC3 49 FF   		EOR	#$FF
AAC5 18      		CLC
AAC6 69 01   		ADC	#$01
AAC8         	THIN40
AAC8 18      		CLC
AAC9 75 B4   		ADC	XINPRS+2,X
AACB 10 02   		BPL	THIN41
AACD A9 00   		LDA	#$00
AACF         	THIN41
AACF C9 10   		CMP	#$10
AAD1 90 02   		BCC	THIN42
AAD3 A9 0F   		LDA	#$0F
AAD5         	THIN42
AAD5 95 B4   		STA	XINPRS+2,X
AAD7 C9 08   		CMP	#$08
AAD9 90 02   		BCC	THIN43
AADB 49 0F   		EOR	#$0F
AADD         	THIN43
AADD 0A      		ASL	A
AADE 95 BA   		STA	ROTTIM,X
AAE0         	THIN44
AAE0 CA      		DEX
AAE1 10 D2   		BPL	THIN39
             	;
AAE3 AD 8E 0C		LDA	GINDEX+2
AAE6 D0 1B   		BNE	THINK2		; NOT A PHOTON
             	;		PHOTON CONVERGENCE
AAE8 A4 62   		LDY	MISDIF		; DIFFICULTY
AAEA B9 85 BF		LDA	PHODIF,Y
AAED AE A4 0A		LDX	ZPOSH+2
AAF0 10 02   		BPL	THINK3
AAF2 29 7F   		AND	#$7F
AAF4         	THINK3
AAF4 8D CA 08		STA	ZINCRE+2
AAF7 09 80   		ORA	#$80
AAF9 AE 73 0A		LDX	YPOSH+2
AAFC 10 02   		BPL	THINK4
AAFE 29 7F   		AND	#$7F
AB00         	THINK4
AB00 8D 99 0B		STA	YINCRE+2
AB03         	THINK2
AB03 A5 76   		LDA	BINTIM
AB05 29 03   		AND	#$03
AB07 F0 2E   		BEQ	THINK5
AB09         	THINK1
AB09 A5 E6   		LDA	GRAPH+2
AB0B F0 04   		BEQ	THIN20		; NOT ON
AB0D A5 EB   		LDA	STFLAG+2
AB0F D0 25   		BNE	THIN14
AB11         	THIN20
             		;		METORITE
AB11 AD 0A D2		LDA	RANDOM
AB14 C9 04   		CMP	#$04
AB16 B0 1E   		BCS	THIN14
AB18 A9 60   		LDA	#$60
AB1A 8D BE 0C		STA	GINDEX+2
AB1D A2 02   		LDX	#$02
AB1F 20 64 B7		JSR	NEWSTR		; DEFINE LIKE A STAR
AB22 A9 3C   		LDA	#60
AB24 85 EB   		STA	STFLAG+2
AB26 A9 88   		LDA	#$88
AB28 8D 68 0B		STA	XINCRE+2
AB2B A9 00   		LDA	#$00
AB2D 8D 2C 0C		STA	HPOS+2		; METEROR FLASH
AB30 8D 99 0B		STA	YINCRE+2
AB33 8D CA 0B		STA	ZINCRE+2
AB36         	THIN14
AB36 60      		RTS
AB37         	THINK5
AB37 A5 A7   		LDA	ZYTOGG
AB39 49 01   		EOR	#$01
AB3B 85 87   		STA	ZYTOGG
AB3D AA      		TAX		; WHICH ZYLON TO THINK
AB3E B5 E9   		LDA	STFLAG,X		; ALREADY ON?
AB40 D0 42   		BNE	THINK6		; YES
             	;		INIT ZYLON
AB42 A5 E9   		LDA	STFLAG+0
AB44 05 EA   		ORA	STFLAG+1
AB46 29 01   		AND	#$01
AB48 A4 90   		LDY	QUADRT
AB4A D9 C9 08		CMP	CHTRAM,Y
AB4D B0 BA   		BCS	THINK1
             	;			OK TO INIT
AB4F A9 FF   		LDA	#$FF
AB51 95 E9   		STA	STFLAG,X
AB53 AD 0A D2		LDA	RANDOM
AB56 29 07   		AND	#$07
AB58 A8      		TAY
AB59 B9 89 BF		LDA	ZYGIND,Y
AB5C 9D 8C 0C		STA	GINDEX+0,X
AB5F A5 62   		LDA	MISDIF
AB61 F0 03   		BEQ	THIN45
AB63 B9 91 BF		LDA	INTSEQ,Y
AB66         	THIN45
AB66 95 A8   		STA	SEQEN,X
AB68 A9 01   		LDA	#$01
AB6A 95 AA   		STA	SEQTIM,X
AB6C 9D AD 09		STA	XSIGN,X
AB6F AD 0A D2		LDA	RANDOM
AB72 25 C7   		AND	JMPMSK
AB74 9D A2 0A		STA	ZPOSH,X
AB77 69 13   		ADC	#$13
AB79 9D 71 0A		STA	YPOSH,X
AB7C 09 71   		ORA	#$71
AB7E 9D 40 0A		STA	XPOSH,X
AB81 20 BE B7		JSR	NEWST4		; Y,Z RANDOM SIGN
AB84         	THINK6
             	;
             	;		SEQUENCER AND TIMEOUT SECTION
             	;
AB84 BD 40 0A		LDA	XPOSH,X
AB87 C9 20   		CMP	#$20
AB89 B0 11   		BCS	THIN27
AB8B BD AD 09		LDA	XSIGN,X
AB8E F0 08   		BEQ	THIN26
AB90 B5 E4   		LDA	GRAPH,X
AB92 F0 08   		BEQ	THIN27
AB94 C9 29   		CMP	#ZYGRF6-ZYGRAF
AB96 F0 04   		BEQ	THIN27
AB98         	THIN26
AB98 A9 00   		LDA	#$00
AB9A 95 A8   		STA	SEQEN,X
AB9C         	THIN27
AB9C D6 AA   		DEC	SEQTIM,X		; TIMEOUT
AB9E 10 24   		BPL	THIN30
ABA0 A9 78   		LDA	#120
ABA2 95 AA   		STA	SEQTIM,X
ABA4 A5 62   		LDA	MISDIF
ABA6 AC 0A D2		LDY	RANDOM
ABA9 C0 30   		CPY	#$30
ABAB 90 01   		BCC	THIN35
ABAD 4A      		LSR	A
ABAE         	THIN35
ABAE 4A      		LSR	A
ABAF 95 B8   		STA	BSTRAF,X
ABB1 B5 A8   		LDA	SEQEN,X
ABB3         	THIN28
ABB3 2C 0A D2		BIT	RANDOM
ABB6 10 02   		BPL	THIN31
ABB8 49 0F   		EOR	#$0F
ABBA         	THIN31
ABBA 95 AC   		STA	XINDES,X
ABBC E8      		INX
ABBD E8      		INX
ABBE E0 06   		CPX	#$06
ABC0 90 F1   		BCC	THIN28
ABC2 A6 A7   		LDX	ZYTOGG		; RESTORE X
ABC4         	THIN30
             	;
             	;		ZYLON STRAFING SECTION
             	;
ABC4 B5 A8   		LDA	SEQEN,X
ABC6 D0 32   		BNE	THIN24
ABC8 A4 A7   		LDY	ZYTOGG
ABCA         	THIN11
ABCA C0 31   		CPY	#RAMNUM
ABCC B0 13   		BCS	THIN12
ABCE B9 B8 00		LDA	BSTRAF,Y
ABD1 4A      		LSR	A
ABD2 B9 40 0A		LDA	XPOSH,Y
ABD5 B0 06   		BCS	THIN36
ABD7 C9 0A   		CMP	#$0A
ABD9 90 0E   		BCC	THIN22
ABDB B0 04   		BCS	THIN12		; JUMP
ABDD         	THIN36
ABDD C9 F5   		CMP	#$F5
ABDF B0 04   		BCS	THIN33
ABE1         	THIN12
ABE1 B9 AD 09		LDA	XSIGN,Y
ABE4 4A      		LSR	A
ABE5         	THIN33
ABE5 A9 0F   		LDA	#$0F
ABE7 B0 02   		BCS	THIN23
ABE9         	THIN22
ABE9 A9 00   		LDA	#$00
ABEB         	THIN23
ABEB 95 AC   		STA	XINDES,X
ABED 18      		CLC
ABEE 98      		TYA
ABEF 69 31   		ADC	#RAMNUM
ABF1 A8      		TAY
ABF2 E8      		INX
ABF3 E8      		INX
ABF4 E0 06   		CPX	#$06
ABF6 90 D2   		BCC	THIN11
ABF8 A6 A7   		LDX	ZYTOGG		; RESTORE X
ABFA         	THIN24
             	;
             	;		ACCELERATION SECTION
             	;
ABFA A4 A7   		LDY	ZYTOGG
ABFC         	THINK8
ABFC B5 B2   		LDA	XINPRS,X
ABFE D5 AC   		CMP	XINDES,X
AC00 F0 08   		BEQ	THINK10
AC02 B0 04   		BCS	THINK9
AC04 F6 B2   		INC	XINPRS,X
AC06 90 02   		BCC	THIN10		; JUMP
AC08         	THINK9
AC08 D6 B2   		DEC	XINPRS,X
AC0A         	THIN10
AC0A 86 6A   		STX	TEMP		; SAVE X
AC0C AA      		TAX
AC0D BD 99 BF		LDA	ZYWARP,X
AC10 A6 6A   		LDX	TEMP		; RESTORE X
AC12 99 66 0B		STA	XINCRE,Y
AC15 98      		TYA
AB16 18      		CLC
AC17 69 31   		ADC	#RAMNUM
AC19 A8      		TAY
AC1A E8      		INX
AC1B E8      		INX
AC1C E0 06   		CPX	#$06
AC1E 90 DC   		BCC	THINK8
AC20 A6 A7   		LDX	ZYTOGG		; RESTORE X
             	;
             	;
             	;		FIRE PHOTON
AC22 AD 8E 0C		LDA	GINDEX+2
AC25 D0 0B   		BNE	THIN16
AC27 A5 EB   		LDA	STFLAG+2
AC29 D0 06   		BNE	THIN13
AC2B A5 BE   		LDA	PHEXWT
AC2D F0 03   		BEQ	THIN16
AC2F C6 BE   		DEC	PHEXWT
AC31         	THIN13
AC31 60      		RTS
AC32         	THIN16
AC32 18      		CLC
AC33 BD A2 0A		LDA	ZPOSH,X
AC36 69 02   		ADC	#$02
AC38 C9 05   		CMP	#$05
AC3A B0 F5   		BCS	THIN13
AC3C A0 D0   		LDY	#$D0
AC3E BD AD 09		LDA	XSIGN,X
AC41 4A      		LSR	A
AC42 BD 40 0A		LDA	XPOSH,X
AC45 B0 08   		BCS	THIN15
AC47 49 FF   		EOR	#$FF
AV49 A4 62   		LDY	MISDIF
AC4B F0 E4   		BEQ	THIN13
AC4D A0 50   		LDY	#$50
AC4F         	THIN15
AC4F C9 20   		CMP	#$20
AC51 B0 DE   		BCS	THIN13
AC53 8C 68 0B		STY	XINCRE+2
AC56 A9 00   		LDA	#$00
AC58 8D 8E 0C		STA	GINDEX+2
AC5B 8D 2C 0C		STA	HPOS+2		; METEOR FLASH
AC5E A9 3E   		LDA	#62
AC60 85 EB   		STA	STFLAG+2
AC62 A2 02   		LDX	#$02
AC64 A4 A7   		LDY	ZYTOGG
AC66 84 BF   		STY	ATTARG
AC68 4C AF AC		JMP	EXHELP
             	;
             	;
             	;
AC6B         	EXPLOS
             	;		INIT EXPLOSION
             	;		Y CONTAINS INDEX OF ZYLON HIT
AC6B A9 80   		LDA	#$80		; 2 SECONDS
AC6D 85 73   		STA	ETIMER
AC6F A2 30   		LDX	#RMLAST
AC71 B6 79   		STX	NSTARS		; LAST STAR FOR EXPLOSION
AC73         	EXPLS1
AC73 AD 0A D2		LDA	RANDOM
AC76 29 0F   		AND	#$0F
AC78 79 2A 0C		ADC	HPOS,Y
AC7B E9 30   		SBC	#$30
AC7D 9D 2A 0C		STA	HPOS,X
AC80 AD 0A D2		LDA	RANDOM
AC83 29 0F   		AND	#$0F
AC85 79 F9 0B		ADC	VPOS,Y
AC88 4A      		LSR	A
AC89 E9 10   		SBC	#$10
AC8B 9D F9 0B		STA	VPOS,X
AC8E 20 AF AC		JSR	EXHELP
AC91 AD 0A D2		LDA	RANDOM
AC94 29 87   		AND	#$87
AC96 9D 66 0B		STA	XINCRE,X
AC99 AD 0A D2		LDA	RANDOM
AC9C 29 87   		AND	#$87
AC9E 9D 97 0B		STA	YINCRE,X
ACA1 AD 0A D2		LDA	RANDOM
ACA4 29 87   		AND	#$87
ACA6 9D C8 0B		STA	ZINCRE,X
ACA9 CA      		DEX
ACAA E0 10   		CPX	#STLAST
ACAC D0 C5   		BNE	EXPLS1
ACAE 60      		RTS
             	;
             	;
ACAF         	EXHELP
             		;	EXPLOSION HELPER
ACAF B9 AD 09		LDA	XSIGN,Y
ACB2 9D AD 09		STA	XSIGN,X
ACB5 B9 40 0A		LDA	XPOSH,Y
ACB8 9D 40 0A		LDA	XPOSH,X
ACBB B9 D3 0A		LDA	XPOSL,Y
ACBE 9D D3 0A		STA	XPOSL,X
ACC1         	EXHLP1		; ENTRY POINT FROM HLINES	*************************
ACC1 B9 DE 09		LDA	XSIGN,Y
ACC4 9D DE 09		STA	XSIGN,X
ACC7 B9 71 0A		LDA	XPOSH,Y
ACCA 9D 71 0A		STA	XPOSH,X
ACCD B9 0F 0A		LDA	ZSIGN,Y
ACC0 9D 0F 0A		STA	ZSIGN,X
             	;
ACD3 B9 A2 0A		LDA	ZPOSH,Y
ACD6 9D A2 0A		STA	ZPOSH,X
ACD9 B9 04 0B		LDA	YPOSL,Y
ACDC 9D 04 0B		STA	YPOSL,X
ACDF B9 35 0B		LDA	ZPOSL,Y
ACE2 9D 35 0B		STA	ZPOSL,X
ACE5         	EXHLP2		; ENTRY POINT FROM BSERVE  **********************
ACE5 60      		RTS
             	;
             	;
             	;
             	;
ACE6         	BSERVE
             	;		STARBASE SERVICE ROUTINE
ACE6 A5 7B   		LDA	BASFLG
ACE8 F0 FB   		BEQ	EXHLP2		; BRANCH TO RTS
ACEA A5 D0   		LDA	DISFLG
ACEC D0 05   		BNE	BSERV9
ACEE A9 14   		LDA	#$14		; PRIORITY FOR FRONT VIEW OF STARBASE
ACF0 8D 1B D0		STA	PRIOR
ACF3         	BSERV9
ACF3 A9 02   		LDA	#$02
ACF5 8D 5C 09		STA	DCSTOR
             	;
ACF8 A9 30   		LDA	#$30
ACFA 8D 8E 0C		STA	GINDEX+2
ACFD A9 20   		LDA	#$20
ACFF 8D 8D 0C		STA	GINDEX+1
AD02 A9 40   		LDA	#$40
AD04 8D 8C 0C		STA	GINDEX+0
AD07 A9 FF   		LDA	#$FF
             	;
AD09 A6 90   		LDX	QUADRT
AD0B BC C9 0B		LDY	CHTRAM,X
AD0E 30 02   		BMI	BSER13
AD10 A9 00   		LDA	#$00
AD12         	BSER13
AD12 85 E9   		STA	STFLAG+0
AD14 85 EA   		STA	STFLAG+1
AD16 85 5B   		STA	STFLAG+2
AD18 85 7B   		STA	BASFLG
AD1A 30 0A   		BMI	BSERV1
AD1C A0 02   		LDY	#$02
AD1E 20 6B AC		JSR	EXPLOS
AD21 A2 0A   		LDX	#NOITB1-NOISTB
AD23 4B A8 AE		JMP	NOISE
AD26         	BSERV1
             		;		TOO CLOSE ?
AD26 AD 42 0A		LDA	XPOSH+2
AD29 D0 0A   		BNE	BSER14
AD2B AD D5 0A		LDA	XPOSL+2
AD2E C9 20   		CMP	#$20
AD30 B0 03   		BCS	BSER14
AD32 EE D5 0A		INC	XPOSL+2
AD35         	BSER14
             	;		ORBIT  ?
AD35 AD 2C 0C		LDA	HPOS+2
AD38 38      		SEC
AD39 E9 78   		SBC	#$78
AD3B C9 10   		CMP	#$10
AD3D B0 22   		BCS	BSERV8
AD3F AD F8 0B		LDA	VPOS+2
AD42 38      		SEC
AD43 E9 68   		SBC	#$68
AD45 C9 10   		CMP	#$10
AD47 B0 18   		BCS	BSERV8
AD49 AD 42 0A		LDA	XPOSH+2
AD4C C9 02   		CMP	#02
AD4E B0 11   		BCS	BSERV8
AD50 AD AF 09		LDA	XSIGN+2
AD53 2D 11 0A		AND	ZSIGN+2
AD56 49 01   		EOR	#$01
AD58 05 71   		ORA	SPEED
AD5A 0D A4 0A		ORA	ZPOSH+2
AD5D 05 71   		ORA	WARP
AD5F F0 10   		BEQ	BSERV3		; IN ORBIT
AD61         	BSERV8
AD61 A5 75   		LDA	BSEQTM		; ORBIT ABORTED
AD63 C9 02   		CMP	#$02
AD65 90 05   		BCC	BSER15
AD67 A0 1F   		LDY	#SENDKA-SENTAB
AD69 20 23 B2		JSR	LDMESS
AD6C         	BSER15
AD6C A9 00   		LDA	#$00
AD6E 85 75   		STA	BSEGTM
AD70         	BSER11
AD70 60      		RTS
             	;
AD71         	BSERV3
AD71 24 75   		BIT	BSEGTM
AD73 70 0D   		BVS	BSERV4
AD75 30 42   		BMI	BSERV5
AD77 A5 75   		LDA	BSEQTM		; LD MESS
AD79 D0 F5   		BNE	BSER11		; NO
AD7B C6 75   		DEC	BSEQTM		; =FF
AD7D A0 1C   		LDY	#SENORB-SENTAB
AD7F 4C 23 B2		JMP	LDMESS
AD82         	BSERV4
AD82 A2 00   		LDX	#$00
AD84 86 65   		STX	REPMSG
AD86 A4 D1   		LDY	SENPTR
AD88 D0 E6   		BNE	BSER11		; WAIT FO MESSAGE TO TIMEOUT
AD8A A9 50   		LDA	#$50
AD8C 8D 90 0C		STA	GINDEX+4
AD8F A9 01   		LDA	#$01
AD91 8D B1 09		STA	XSIGN+4
AD94 8D E2 09		STA	YSIGN+4
AD97 8D 13 0A		STA	ZSIGN+4
AD9A 8D A6 0A		STA	ZPOSH+4
AD9D 8D 9B 0B		STA	YINCRE+4
ADA0 A9 10   		LDA	#$10
ADA2 8D 44 0A		STA	XPOSH+4
ADA5 A9 00   		LDA	#$00
ADA7 8D 75 0A		STA	YPOSH+4
ADAA A9 87   		LDA	#$87
ADAC 8D 6A 0B		STA	XINCRE+4
ADAF A9 81   		LDA	#$81
ADB1 85 75   		STA	BSEQTM
ADB3 8D CC 0B		STA	ZINCRE+4
ADB6 85 ED   		STA	STFLAG+4
ADB8         	BSERV7
ADB8 60      		RTS
ADB9         	BSERV5
ADB9 AD B1 09		LDA	XSIGN+4		; SHIP DOCKED ?
ADBC D0 FA   		BNE	BSERV7		; NO
ADBE A2 0C   		LDX	#CH4TB3-CH4TAB		; SOUND
ADC0 20 A6 B3		JSR	NOTINT
ADC3 A0 21   		LDY	#SENETC-SENTAB
ADC5 20 23 B2		JSR	LDMESS
             	;		CLEAR	DAMAGE
ADC8 A2 05   		LDX	#$05
ADCA         	BSER12
ADCA BD 8B BB		LDA	STINIT+73,X
ADCD 9D 92 09		STA	DAMAGE,X
ADD0 CA      		DEX
ADD1 10 F7   		BPL	BSER12
             	;
             	;		NEW ENERGY
ADD3 A9 89   		LDA	#$89
ADD5 A2 03   		LDX	#$03
ADD7         	BSER20
ADD7 9D 55 09		STA	DENERG+0,X
ADDA CA      		DEX
ADDB 10 FA   		BPL	BSER20
ADDD A9 07   		LDA	#$07
ADDF 8D 6A 0B		STA	XINCRE+4
ADE2 A9 81   		LDA	#$81
ADE4 8D 9B 0B		STA	YINCRE+4
ADE7 A9 01   		LDA	#$01
ADE9 8D CC 0B		STA	ZINCRE+4
ADEC 85 75   		STA	BSEQTIM
ADEE 4C 7B B0		JMP	KEYSR7		; RE-LOAD INSET
             	;
             	;
             	;
             	;
ADF1         	LDISP
             	;	LOAD DISPLAY LISTS
             	;	A=#OF BYTES TO STORE, X=POSIT IN DSPLY, Y=PNTR IN LISTAB
ADF1 78      		SEI		; WE DONT WANT NO INTERUPTS !!
ADF2 85 6A   		STA	TEMP
ADF4         	LDISP3
ADF4 AD 0B D4		LDA	VCOUNT		; CHECK IF ANTIC IS IN SAFE AREA
ADF7 C9 7C   		CMP	#DISTOP
ADF9 90 F9   		BCC	LDISP3
ADFB         	LDISP2
ADFB B9 62 BA		LDA	LISTAB,Y
ADFE C8      		INY
ADFF 10 02   		BPL	LDISP1
AE01 A9 0D   		LDA	#$0D
AE03         	LDISP1
AE03 9D 80 02		STA	DISPLY,X
AE06 E8      		INX
AE07 C6 6A   		DEC	TEMP
AE09 D0 F0   		BNE	LDISP2
AE0B 58      		CLI			; IRQS BACK ON  !!
AE0C 60      		RTS
             	;
             	;
             	;
             	;
             	;
             	;
             	;
             	;
AE0D         	CLRMAP
             	;		CLEAR MEMORY MAP SUBROUTINE
AE0D A9 10   		LDA	#MEMMAP/256
AE0F         	CLRMP1		; ENTRY POINT CLEAR ALL RAM  ************************
AE0F 85 69   		STA	PNTR+1
AE11 A9 00   		LDA	#$00
AE13 A8      		TAY
AE14 85 68   		STA	PNTR
AE16 85 A3   		STA	LOKFLG		; LOCK FLAG IS CLEARED
AE18 85 7A   		STA	CNSTAR		; RAM HAS BEEN CLEARED
AE1A         	CLRMP2
AE1A 91 68   		STA	(PNTR),Y
AE1C C8      		INY
AE1D D0 FB   		BNE	CLRMP2
AE1F E6 69   		INC	PNTR+1
AE21 A4 69   		LDY	PNTR+1
AE23 C0 20   		CPY	#$20
AE25 A8      		TAY		; RE-ZERO Y REG
AE26 90 F2   		BCC	CLRMP2
AE28 60      		RTS
             	;
             	;
AE29         	PHOTON
             	;		PHOTON TORPEDO FIRE
AE29 A5 84   		LDA	PHOFLG		; REPEAT FLAG
AE2B AC 10 D0		LDY	TRIG0		; SHOOT ?
AE2E 84 84   		STY	PHOFLG
AE30 D0 0E   		BNE	PHOTN2		; NO
AE32 84 66   		STY	TIMOUT		; RESET ATRACT TIMEOUT
AE34 A6 C0   		LDX	HFLAG		; HWARP ?
AE36 D0 08   		BNE	PHOTN2		; YES, NO FIRE
AE38 A6 87   		LDX	PHOTOG
AE3A C9 01   		CMP	#$01
AE3C F0 03   		BEQ	PHOTN8
AE3E B0 18   		BCS	PHOTN4
AE40         	PHOTN2
AE40 60      		RTS
AE41         	PHOTN8
             	;		ONE-SHOT
AE41 B5 EC   		LDA	STFLAG+3,X		; ONE-SHOT TIMEOUT
AE43 C9 E8   		CMP	#$E8		; ALL DONE ?
AE45 B0 F9   		BCS	PHOTN2		; NO
AE47 AC 5C 09		LDY	DCSTOR
AE4A 84 89   		STY	LOKTAR
AE4C A9 0C   		LDA	#12
AE4E A4 A3   		LDY	LOKFLG
AE50 84 86   		STY	LOKLOC
AE52 F0 02   		BEQ	PHOTN3
AE54 A9 00   		LDA	#$00
AE56         	PHOTN3
AE56 85 88   		STA	LOKWAT
AE58         	PHOTN4
AE58 84 84   		STY	PHOFLG
             	;
AE5A 2C 92 09		BIT	DAMAGE+0
AE5D 70 E1   		BVS	PHOTN2
AE5F 30 05   		BMI	PHOTN7
AE61 8A      		TXA
AE62 49 01   		EOR	#$01
AE64 85 87   		STA	PHOTOG
AE66         	PHOTN7
AE66 8A      		TXA
AE67 9D E1 09		STA	YSIGN+3,X		; NEW YSIGN
AE6A BD 73 BF		LDA	PHOYPS,X		; NEW YPOSH
AE6D 9D 74 0A		STA	YPOSH+3,X
AE70 A9 FF   		LDA	#$FF
AE72 95 EC   		STA	STFLAG+3,X		; INIT PHOTON TIME
AE74 9D A5 0A		STA	ZPOSH+3,X
AE77 A9 00   		LDA	#$00
AE79 9D 8F 0C		STA	GINDEX+3,X		; INIT PHOTON GRAPHIC
AE7C 9D 43 0A		STA	XPOSH+3,X
AE7F 9D 07 0B		STA	YPOSL+3,X
AE82 9D 12 0A		STA	ZSIGN+3,X
AE85 9D 38 0B		STA	ZPOSL+3,X
AE88 A9 01   		LDA	#$01
AE8A 9D B0 09		STA	XSIGN+3,X
AE8D 9D D9 0A		STA	XPOSL+3,X
AE90 A5 D0   		LDA	DISFLG
AE92 4A      		LSR	A
AE93 6A      		ROR	A
AE94 09 66   		ORA	#$66
AE96 9D 69 0B		STA	XINCRE+3,X
AE99 A9 00   		LDA	#$00
AE9B 9D 9A 0B		STA	YINCRE+3,X
AE9E 9D CB 0B		STA	ZINCRE+3,X
AEA1 A2 02   		LDX	#$02
AEA3 20 6F B8		JSR	PANDS6			; PHOTON ENERGY
AEA6 A2 00   		LDX	#$00
             	;
             	;		FALL THROUGH TO NOISE  ************************
             	;
AEA8         	NOISE
             	;		NOISE INIT, X=NOISTB PNTR
AEA8 8A      		TXA		; PHOTONS
AEA9 D0 06   		BNE	NOISE1		; NO
             		;	PHOTONS HAVE LOWER PRIORITY THAN EXPLOSIONS

AEAB A5 E1   		LDA	AUDTIM
AEAD C9 18   		CMP	#$18
AEAF B0 18   		BCS	NOISE2
AEB1         	NOISE1
AEB1 A0 07   		LDY	#$07
AEB3         	NOISE3
AEB3 BD 20 BF		LDA	NOISTB,X
AEB6 99 DA 00		STA	PHOREP,Y
AEB9 E8      		INX
AEBA 88      		DEY
AEBB 10 FB   		BPL	NOISE3
AEBD BD 20 BF		LDA	NOISTB,X
AEC0 8D 08 D2		STA	AUDCTL
AEC3 BD 21 BF		LDA	NOISTB+1,X
AEC6 8D 04 D2		STA	AUDF3
AEC9         	NOISE2
AEC9 60      		RTS

             	;
             	;
AECA         	POHELP
             	;		PHOTON HELPER
AECA A0 80   		LDY	#$80
AECC B0 04   		BCS	POHLP1
AECE 49 FF   		EOR	#$FF
AED0 A0 00   		LDY	#$00
AED2         	POHLP1
AED2 84 6A   		STY	TEMP
AED4 C0 08   		CMP	#$08
AED6 90 02   		BCC	POHLP2
AED8 A9 07   		LDA	#$07
AEDA         	POHLP2
AEDA A8      		TAY
AEDB A5 6A   		LDA	TEMP
AEDD 19 C9 BF		ORA	PHVECT,Y
AEE0 60      		RTS
             	;
             	;
             	;
AEE1         	DAMCTL
             	;		DAMAGE CONTROL ROUTINE
AEE1 24 64   		BIT	ATRACT
AEE3 30 57   		BMI	DAMCT1		; GAME OVER NO DAMAGE
AEE5 A6 62   		LDX	MISDIF
AEE7         	DAMCT2
AEE7 AD 0A D2		LDA	RANDOM
AEEA DD 10 BF		CMP	DPRBTB,X
AEED B0 4D   		BCS	DAMCT1
AEEF 29 07   		AND	#$07
AEF1 C9 06   		CMP	#$06
AEF3 B0 47   		BCS	DAMCT1
AEF5 AA      		TAX
AEF6 BD 92 09		LDA	DAMAGE,X
AEF9 0A      		ASL	A
AEFA 30 EB   		BMI	DAMCT2
AEFC A5 EB   		LDA	STFLAG+2
AEFE C9 1E   		CMP	#30
AF00 A9 80   		LDA	#$80
AF02 BC 14 BF		LDY	DAMGTB,X
AF05 90 17   		BCC	DAMCT3
AF07 E0 03   		CPX	#$03
AF09 D0 05   		BNE	DAMCT5
AF0B 2C 96 09		BIT	DAMAGE+4
AF0E 70 0E   		BVS	DAMCT3
AF10         	DAMCT5
AF10 E0 04   		CPX	#$04
AF12 D0 05   		BNE	DAMCT6
AF14 2C 95 09		BIT	DAMAGE+3
AF17 70 05   		BVS	CAMCT3
AF19         	DAMCT6
AF19 A9 C0   		LDA	#$C0
AF1B BC 1A BF		LDY	DESTTB,X
AF1E         	DAMCT3
AF1E 1D 92 09		ORA	DAMAGE,X
AF21 9D 92 09		STA	DAMAGE,X
AF24 84 65   		STY	REPMSG
AF26 2C 95 09		BIT	DAMAGE+3
AF29 50 07   		BVC	DAMCT4
AF2B A9 00   		LDA	#$00
AF2D 85 7E   		STA	ATENER
AF2F 20 0D AE		JSR	CLRMAP
AF32         	DAMCT4
AF32 A0 52   		LDY	#SENDMC-SENTAB
AF34 20 23 B2		JSR	LDMESS
AF37 A2 12   		LDX	#CH4TB4-CH4TAB		; DAMAGE
AF39 20 A6 B3		JSR	NOTINT
AF3C         	DAMCT1
AF3C 60      		RTS
             	;
             	;
AF3D         	HITZYL
             	;		PHOTON HIT ZYLON CHECK
AF3D A2 02   		LDX	#$02		; 2 PLAY PHOTONS
AF3F         	HITZY2
AF3F CA      		DEX
AF40 10 01   		BPL	HITZY1
AF42 60      		RTS
AF43 BD BF 0C	HITZY1	LDA	GINDEX+3,X		; PHOTON ?
AF46 D0 F7   		BNE	HITZY2			; NO
AF48 B5 EC   		LDA	STFLAG+3,X		; PHOTON ON ?
AF4A F0 F3   		BEQ	HITZY2		; NO
AF4C B5 82   		LDA	PHITS+0,X		; ANY HIT ?
AF4E 29 07   		AND	#$07		; LOOK AT 0,1 ONLY
AF50 F0 ED   		BEQ	HITZY2		; NO HIT
AF52 4A      		LSR	A		; 0 OR 1 ONLY
AF53 C9 03   		CMP	#$03
AF55 D0 01   		BNE	HITZY9
AF57 4A      		LSR	A
AF58         	HITZY9
AF58 A8      		TAY			; OBJECT INDEX IN Y
AF59 B9 E9 00		LDA	STFLAG,Y		; SHIP ON ?
AF5C F0 E1   		BEQ	HITZY2			; NO
AF5E A5 D0   		LDA	DISFLG
AF60 F0 02   		BEQ	HITZY8
AF62 A9 FF   		LDA	#$FF
AF64         	HITZY8
AF64 85 6C   		STA	TEMP2
AF66 59 40 0A		EOR	XPOSH,Y
AF69 C9 10   		CMP	#$10
AF6B 90 02   		BCC	HITZY3
AF6D A9 0F   		LDA	#$0F
AF6F         	HITZY3
AF6F 4A      		LSR	A
AF70 84 6B   		STY	TEMP1
AF72 A8      		TAY
AF73 A5 6C   		LDA	TEMP2
AF75 5D 43 0A		EOR	XPOSH+3,X
AF78 D9 75 BF		CMP	PHPOST,Y		; TOP BOUND
AF7B B0 C2   		BCS	HITZY2
AF7D D9 7D BF		CMP	PHPOSB,Y		; BOTTOM BOUND
AF80 90 BD   		BCC	HITZY2
AF82 A4 6B   		LDY	TEMP1
             	;		A HIT  !!!
AF84 38      		SEC
AF85 A9 FF   		LDA	#$FF
AF87 F5 EC   		SBC	STFLAG+3,X
AF89 85 E2   		STA	EXPDEL		; AUDIO
AF8B C9 0F   		CMP	#15
AF8D 90 05   		BCC	HITZ11
AF8F B9 8C 0C		LDA	GINDEX,Y
AF92 C9 80   		CMP	#$80
AF94         	HITZ11
AF94 A9 00   		LDA	#$00
AF96 85 88   		STA	LOKWAT
AF98 95 EC   		STA	STFLAG+3,X		; PHOTON OFF
AF9A B0 4B   		BCS	HITZ10
AF9C 99 E9 00		STA	STFLAG,Y		; ZYLON OFF
AF9F B9 8C 0C		LDA	GINDEX,Y
AFA2 F0 43   		BEQ	HITZ10		; PHOTON
AFA4 C9 60   		CMP	$#60		; METORER
AFA6 F0 3F   		BEQ	HITZ10		; YES
AFA8 A9 00   		LDA	#$00
AFAA 85 86   		STA	LOKLOC		; TURN OFF PHOTONS TRACKING
AFAC A6 90   		LDX	QUADRT		; WHICH QUAD KILL IN
AFAE DE C9 08		DEC	CHTRAM,X		; REMOVE FROM CHART
AFB1 10 13   		BPL	HITZY4
AFB3 A9 00   		LDA	#$00		; JUST BLASTED A STARBASE ELSE IMPOSSIBLE
             	;					TO GET HERE
AFB5 9D C9 08		STA	CHTRAM,X
AFB8 38      		SEC
AFB9 A5 CB   		LDA	RATING
AFBB E9 03   		SBC	#3
AFBD 85 CB   		STA	RATING
AFBF A5 CC   		LDA	RATING+1
AFC1 E9 00   		SBC	#$00
AFC3 85 CC   		STA	RATING+1
AFC5 60      		RTS
AFC6         	HITZY4
             	;
             	;		INCKIL
             	;		INCRE KILL COUNT DISPLAY
AFC6 18      		CLC
AFC7 A5 CB   		LDA	RATING
AFC9 69 06   		ADC	#$06
AFCB 85 CB   		STA	RATING
AFCD A5 CC   		LDA	RATING+1
AFCF 69 00   		ADC	#$00
AFD1 85 CC   		STA	RATING+1
AFD3 A2 01   		LDX	#$01
AFD5         	INCKL1
AFD5 FE 50 09		INC	DKILL,X		; KILL BYTE INCRE
AFD8 BD 50 09		LDA	DKISLL,X
AFDB C9 4A   		CMP	#$4A		; BCD OBERFFLOW
AFDD 90 08   		BCC	INCKL2		; NO.
AFDF A9 40   		LDA	#$40		; BCD 0
AFE1 9D 50 09		STA	DKILL,X
AFE4 CA      		DEX
AFE5 10 EE   		BPL	INCKL1		; NEXT BYTE
AFE7         	INCKL2
             	;
AFE7         	HITZ10
AFE7 20 6B AC		JSR	EXPLOS
AFEA A2 7F   		LDX	#127
AFEC         	HITZY5
AFEC BD C9 08		LDA	CHTRAM,X
AFEF 30 02   		BMI	HITZY6
AFF1 D0 0A   		BNE	HITZY7
AFF3         	HITZY6
AFF3 CA      		DEX
AFF4 10 F6   		BPL	HITZY5
             	;		WIN
AFF6 A0 3F   		LDY	#SENWIN-SENTAB
AFF8 A2 00   		LDX	#$00
AFFA 20 21 B1		JSR	CRATE1
AFFD         	HITZY7
AFFD 60      		RTS
             	;
             	;
             	;
             	;
             	;
AFFE         	KEYSERV
             	;		KEYBOARD SERVICE ROUTINE
AFFE A5 CA   		LDA	THEKEY		; ANY KEY
B000 F0 3E   		BEQ	KESR3		; NO
B002 A2 14   		LDX	#$14		; LAST KEY
B004 85 6A   		STA	TEMP
B006 A9 00   		LDA	#$00
B008 85 66   		STA	TIMOUT		; RESET ATRACT TIMEOUT
B00A 85 CA   		STA	THEKEY		; TURN OFF KEY
B00C A9 11   		LDA	#$11
B00E 8D 1B D0		STA	PRIOR		; RESET PRIORITY , FROM STARBASE
B011         	KEYSR1
B011 BD BE BA		LDA	CODCON,X		; KEY CODES
B014 C5 6A   		CMP	TEMP
B016 F0 08   		BEQ	KEYSR2
B018 CA      		DEX
B019 10 F6   		BPL	KEYSR1		; NEXT KEY
             	;			NO KEY
B01B A0 10   		LDY	#SENWHT-SENTAB		; WHAT
B01D 4C 23 B2		JMP	LDMESS
B020         	KEYSR2			; KEY FOUND
B020 E0 0A   		CPX	#$0A		; IMPULSE ENGINE ?
B022 B0 1D   		BCS	KEYSR4		; NO
B024 A5 C0   		LDA	HFLAG		; HWARP ?
B026 F0 03   		BEQ	KEYS20		; NO
B028 4C 80 A9		JMP	HABORT
B02B         	KEYS20
B02B 2C 93 09		BIT	DAMAGE+1		; ENGINES
B02E 50 06   		BVC	KEYS23
B030 E0 06   		CPX	#$06
B032 90 02   		BCC	KEYS23
B034 A2 05   		LDX	#$05
B036         	KEYS23
B036 BD D3 BA		LDA	WENTAB,X
B039 85 80   		STA	WPENER		; IMPULSE ENGINE ENERGY
B03B BD B4 BA		LDA	WARPTB,X		; SPEED
B03E 85 71   		STA	WARP		; SPEED DESIRED
B040         	KEYSR3
B040 60      		RTS
B041         	KEYSR4
B041 E0 0E   		CPX	#$0E		; DISPLAY TYPE KEY ?
B043 B0 1B   		BCS	KEYSR5		; NO
             	;
B045         	KEYS15		; ENTRY POINT TO INIT DISPLAY,  ***********************
             	;		X MUST BE DEFINED TO THE KEY CODE IN CODCON
B045 BD 18 8E		LDA	DISTYP-10,X
B048 85 D0   		STA	DISFLG
B04A BC 82 BA		LDY	DISDIS-10,X
B04D A2 02   		LDX	#DISPL1-DISPLY
B04F A9 08   		LDA	#$08
B051 20 F1 AD		JSR	LDISP
             	;
B054 A2 10   		LDX	#STLAST
B056         	KEYSR6
B056 20 64 B7		JSR	NEWSTR
B059 CA      		DEX
B05A E0 05   		CPX	#OBJNUM
B05C B0 F8   		BCS	KEYSR6
B05E 90 1B   		BCC	KEYSR7		; JUMP
B060         	KEYSR5
B060 E0 11   		CPX	#$11		; TOGGLE TYPE ?
B062 B0 35   		BCS	KEYSR8		; NO
B064 BC 18 BE		LDY	TOFFMG-$0E,X
B067 B5 6E   		LDA	TRKFLG-$0E,X
B069 5D 1B BE		EOR	TOGTAB-$0E,X
B06C 95 6E   		STA	TRKFLG-$0E,X
B06E F0 03   		BEQ	KEYSR9
B070 BC 1E BE		LDY	TONMSG-$0E,X
B073         	KEYSR9
B073 20 23 B2		JSR	LDMESS
B076 A2 0C   		LDX	#CH4TB3-CH4TAB		; KEYS
B078 20 A6 B3		JSR	NOTINT
B07B         	KEYSR7		; ENTRY POINT FOR RE-LOADING INSET  ***********
B07B A2 16   		LDX	#$16
B07D A4 7C   		LDY TRKFLG
B07F F0 01   		BEQ	KEYS18
B081 E8      		INX
B082         	KEYS18
B082 8E 5A 09		STX	DCSTOR-2
B085 20 0D AE		JSR	CLRMAP
B088 A5 7E   		LDA	ATENER
B08A F0 B4   		BEQ	KEYSR3
B08C A6 D0   		LDX	DISFLG
B08E F0 06   		BEQ	KEYS10
B090 E0 01   		CPX	#$01
B092 D0 AC   		BNE	KEYSR3
B094 A2 2A   		LDX	#INSTB1-INSTAB
B096         	KEYS10
B096 4C 6F A7		JMP	LDINST
B099         	KEYSR8
B099 E0 11   		CPX	#$11		; HYPERWARP ?
B09B D0 50   		BNE	KEYS13
B09D A5 C0   		LDA	HFLAG		; HWARP ALREADY ON ?
B09F D0 5A   		BNE	KEYS14
B0A1 A9 7F   		LDA	#$7F
B0A3 85 C0   		STA	HFLAG
B0A5 A9 FF   		LDA	#$FF
B0A7 85 71   		STA	WARP
B0A9 A9 1E   		LDA	#30
B0AB 85 80   		STA	WPENER
B0AD A9 30   		LDA	#RMLAST
B0AF 85 C3   		STA	HPNTR
             	;		H STEERING STUFF
B0B1 A9 00   		LDA	#$00
B0B3 85 C2   		STA	HTIMER
B0B5 8D 74 0A		STA	YPOSH+3
B0B8 8D 07 0B		STA	YPOSL+3
B0BB 8D 38 0B		STA	ZPOSL+3
B0BE 8D 69 0B		STA	XINCRE+3
B0C1 A9 01   		LDA	#$01
B0C3 8D B0 09		STA	XSIGN+3
B0C6 8D E1 09		STA	YSIGN+3
B0C9 8D 12 0A		STA	ZSIGN+3
B0CC 8D A5 0A		STA	ZPOSH+3
B0CF A5 8F   		LDA	HYHPOS
B0D1 85 C4   		STA	HSTEER
B0D3 A5 8E   		LDA	HYVPOS
B0D5 85 C5   		STA	VSTEER
B0D7 A5 62   		LDA	MISDIF
B0D9 F0 0B   		BEQ	KEYS24
B0DB A5 91   		LDA	HYPENG
B0DD 2A      		ROL	A
B0DE 2A      		ROL	A
B0DF 2A      		ROL	A
B0E0 29 03   		AND	#$03
B0E2 A8      		TAY
B0E3 B9 D7 BE		LDA	STERTB,Y		; DIFFICULTY
B0E6         	KEYS24
B0E6 85 C6   		STA	STERMK
             	;		END STUFF
B0E8 A0 11   		LDY	#SENHYP-SENTAB		; MESSAGE HYPER WARP ENGAGED
B0EA 4A 23 B2		JMP	LDMESS
B0ED         	KEYS13
B0ED E0 13   		CPX	#$13
B0EF B0 0B   		BCS	KEYS27		; PAUSE
B0F1 AD 5C 09		LDA	DCSTOR
B0F4 49 01   		EOR	#$01
B0F6 29 01   		AND	#$01
B0F8 8D 5C 09		STA	DCSTOR
B0FB         	KEYS14
B0FB 60      		RTS
B0FC         	KEYS27
B0FC D0 08   		BNE	KEYS28
B0FE AD 00 D3		LDA	PORTA		; PAUSE UNTIL MOVE JOYSTICK
B101 C9 FF   		CMP	#$FF
B103 F0 F7   		BEQ	KEYS27
B105 60      		RTS
B106         	KEYS28
             	;		MISSION ABORTED
B106 A0 76   		LDY	#SENABR-SENTAB
B108 A2 04   		LDX	#$04
             	;
             	;		FALL THROUGH TO CRATE  ************************
             	;
             	;
B10A         	CRATE
             	;		CALCULATE RATING, X=0 MISSION COMPLETE, 4=ABORTED, 8-DESTROYED
             	;	Y=MESSAGE TYPE
             	;		GAME OVER, CALCULATE RATING

B10A A9 00   		LDA	#$00
B10C 85 EC   		STA	STFLAG+3		; NO HWARP CURSOR
B10E 85 D6   		STA	NPRIOR
B110 85 D1   		STA	SENPTR
B112 85 8B   		STA	REDFLG
B114 8D 07 D2		STA	AUDC4
B117 85 71   		STA	WARP
B119 85 81   		STA	SPABAK
B11B 85 7D   		STA	SHENER
B11D 85 C0   		STA	HFLAG
B11F 85 C1   		STA	HISPED
B121         	CRATE1		; ENTRY POINT FOR A GOOD MISSION  **********************
B121 A9 FF   		LDA	#$FF
B123 85 64   		STA	ATRACT
B125 84 65   		STY	REPMSG		; REPEAT MESSAGE
B127 8A      		TXA
B128 05 62   		ORA	MISDIF		; MISSION DIFF GAME RESULT
B12A AA      		TAX
B12B BD DD BE		LDA	DIFTAB,X
B12E 1B      		CLC
B12F 65 CB   		ADC	RATING
B131 AA      		TAX
B132 A9 00   		LDA	#$00
B134 85 C9   		STA	VERJOY
B136 85 C8   		STA	HORJOY
B13A 65 CC   		ADC	RATING+1
B13C 4A      		LSR	A
B13D 8A      		TXA
B13E 6A      		ROR	A
B13F 4A      		LSR	A
B140 4A      		LSR	A
B141 4A      		LSR	A
B142 C9 13   		CMP	#$13
B144 90 04   		BCC	CRATE2
B146 A9 12   		LDA	#$12
B148 A2 0F   		LDX	#$0F
B14A         	CRATE2
B14A 85 CD   		STA	ENDRAT
B14C A8      		TAY
B14D 8A      		TXA
B14E C0 00   		CPY	#$00
B150 F0 0B   		BEQ	CRATE4
B152 C0 0B   		CPY	#$0B
B154 90 04   		BCC	CRATE5
B156 C0 0F   		CPY	#$0F
B158 90 03   		BCC	CRATE4
B15A         	CRATE5
B15A 4A      		LSR	A
B15B 49 08   		EOR	#$08
B15D         	CRATE4
B15D 29 0F   		AND	#$0F
B15F 85 CE   		STA	ENDCLS
B161         	CRATE3
B161 60      		RTS

             	;
             	;
             	;
B162         	CSERVE
             	;		SERVICE GALACTIC CHART
B162 A5 C0   		LDA	HFLAG		; HWARP ON ?
B164 D0 04   		BNE	CSERV9		; YES
B166 A5 D0   		LDA	DISFLG		; DOING GALACTIC CHART ?
B168 30 01   		BMI	CSERV1		; NO
B16A         	CSERV9
B16A 60      		RTS
B16B         	CSERV1
B16B 2C 97 09		BIT	DAMAGE+5		; COMMUNICATIONS
B16E 30 03   		BMI	CSER10
B170 20 B9 B4		JSR	LDGALT		; LD UP THE CHART
B173         	CSER10
B173 A5 72   		LDA	TIMERX		; SLOW DOWN CURSOR MOVE
B175 29 01   		AND	#$01
B177 D0 2E   		BNE	CSERV8
B179 18      		CLC		; UPDATE HORIZ CURSOR POS
B17A A5 BF   		LDA	HYHPOS
B17C 65 C8   		ADC	HORJOY
B17E 29 7F   		AND	#$7F
B180 85 8F   		STA	HYHPOS
B182 18      		CLC
B183 69 3D   		ADC	#HORCHT		; OFFSET TO POSITION ON SCREEN
B185 8D 2E 0C		STA	HPOS+4		; PLAYER FOUR IS CURSOR
B188 18      		CLC			; UPDATE VERT CURSOR POSITION
B189 A5 8E   		LDA	HYVPOS
B18B 65 C9   		ADC	VERJOY
B18D 29 7F   		AND	#$7F
B18F 85 8E   		STA	HYVPOS
B191 18      		CLC			; OFF SET TO POSITION ON SCREEN
B192 69 3F   		ADC	#VERCHT
B194 8D FD 0B		STA	VPOS+4
             	;				SHIP POS TO OBJ3
B197 A5 8C   		LDA	GVPOS
B199 18      		CLC
B19A 69 3F   		ADC	#VERCHT
B19C 8D FC 08		STA	VPOS+3
B19F A5 8D   		LDA	GHPOS
B1A1 18      		CLC
B1A2 69 3D   		ADC	#HORCHT
B1A4 8D 2D 0C		STA	HPOS+3
             	;		CLACULATE CURSORS QUADRANT
             	;
B1A7         	CSERV8		; ENTRY POINT FOR CALCULATING NEW ENERGY AND QUADRANT  ******
B1A7 A5 8F   		LDA	HYHPOS		; HPOS
B1A9 4A      		LSR	A
B1AA 4A      		LSR	A
B1AB 4A      		LSR	A
B1AC 85 6A   		STA	TEMP		;TEMP STORE H COMP
B1AE A5 8E   		LDA	HYVPOS		; VPOS
B1B0 29 70   		AND	#$70		; VCOMP
B1B2 05 6A   		ORA	TEMP		; ADD HCOMP
B1B4 85 92   		STA	HYPQAD		; QUADRANT CALCULATED
             	;			CALCULATE NUMBER OF ZYLONS IN TARGET
B1B6 AA      		TAX
B1B7 BD C9 08		LDA	CHTRAM,X		; WHATS IN QUAD
B1BA 10 02   		BPL	CSERV2		; STARBASE ?
B1BC A9 00   		LDA	#$00		; YES
B1BE         	CSERV2
B1BE 09 90   		ORA	#$90		; COLOR AND ASCII CODE
B1C0 2C 97 09		BIT	DAMAGE+5
B1C3 70 03   		BVS	CSER11
B1C5 8D 8D 09		STA	DTARG		; DISPLAY NUMBER OF ZYLONS
B1C8         	CSER11
             	;		CALCULATE WARP ENERGY
B1C8 38      		SEC
B1C9 A5 8F   		LDA	HYHPOS
B1CB E5 8D   		SBC	GHPOS
B1CD B0 04   		BCS	CSERV3
B1CF 49 FF   		EOR	#$FF
B1D1 69 01   		ADC	#$01
B1D3         	CSERV3
B1D3 85 AA   		STA	TEMP
             	;
B1D5 38      		SEC
B1D6 A5 8E   		LDA	HYVPOS
B1D8 E5 8C   		SBC	GVPOS
B1DA B0 04   		BCS	CSERV4
B1DC 49 FF   		EOR	#$FF
B1DE 69 01   		ADC	#$01
B1E0         	CSERV4
B1E0 4A      		LSR	A
B1E1 18      		CLC
B1E2 65 6A   		ADC	TEMP
B1E4 A8      		TAY
B1E5 4A      		LSR	A
B1E6 4A      		LSR	A
B1E7 4A      		LSR	A
B1E8 AA      		TAX
B1E9 98      		TYA
B1EA 29 03   		AND	#$03
B1EC 18      		CLC
B1ED 7D DD DA		ADC	ENGTAB,X
             	;
B1F0 85 91   		STA	HYPENG
B1F2 A8      		TAY
B1F3 A9 10   		LDA	#$10
B1F5 8D 7D 09		STA	DWENER+0
B1F8 8D 7E 09		STA	DWENER+1
B1FB 8D 7F 09		STA	DWENER+2
B1FE         	CSERV6
B1FE A2 02   		LDX	#$02
B200         	CSERV5
B200 FE 7D 09		INC	DWENER,X
B203 BD 7D 09		LDA	DWENER,X
B206 C9 1A   		CMP	#$1A
B208 90 08   		BCC	CSERV7
B20A A9 10   		LDA	#$10
B20C 9D 7D 09		STA	DWENER,X
B20F CA      		DEX
B210 10 EE   		BPL	CSERV5
B212         	CSERV7
B212 88      		DEY
B213 D0 E9   		BNE	CSERV6
B215 60      		RTS
             	;
             	;
             	;
B216         	MSERVE
             	;		SERVICE MESSAGE
B216 A5 D1   		LDA	SENPTR		; MESSAGE ON ?
B218 F0 05   		BEQ	LDMS14		; NO
B21A C6 CF   		DEC	MESTIM		; TIMED OUT ?
B21C F0 10   		BEQ	LDMES1		; YES
B21E         	LDMES2
B21E 60      		RTS
B21F         	LDMES14
B21F A4 65   		LDY	REPMSG		; REPEAT THE MESSAGE ?
B221 F0 FB   		BEQ	LDMES2		; NO
B223         	LDMESS		; ENTRY POINT TO INIT MESSAGE  **********************
B223 84 D1   		STY	SENPTR
B225 A0 23   		LDY	#LISTB6-LISTAB
B227 A2 0F   		LDX	#DISPL2-DISPLY
B229 A9 07   		LDA	#$07
B22B 20 F1 AD		JSR	LDISP		; REVISE DISPLAY LIST FOR MESSAGE
B22E         	LDMES1
B22E A2 13   		LDX	#19		; CLEAR MESSAGE RAM
B230 A9 00   		LDA	#$00
B232 85 6B   		STA	TEMP1		; CLEAR DISPLAY POINTER
B234         	LDMES3
B234 9D 1F 0D		STA	MESAGE,X
B237 CA      		DEX
B238 10 FA   		BPL	LDMES3
B23A         	LDMES4		; MESSAGE LOOP POINT
B23A A6 D1   		LDX	SENPTR		; NEW WORD PNTR
B23C E6 D1   		INC	SENPTR		; ADVANCE TO NEXT WORD
B23E D0 09   		BNE	LDMES5
             	;		MESSAGE DONE
B240 A2 0F   		LDX	#DISPL2-DISPLY
B242 A0 80   		LDY	#$80
B244 A9 07   		LDA	#$07
B246 4C F1 AD		JMP	LDISP		; RESTORE DISPLAY LIST
B249         	LDMES5
B249 BD AA BB		LDA	SENTAB,X		; A =NEW WORD
B24C C9 FC   		CMP	#$FC		; CLASS ?
B24E D0 0F   		BNE	LDMES6		; NO
B250 A4 CE   		LDY	ENDCLS
B252 B9 FC BE		LDA	CLASTB,Y	; VALUE 1-5, IN DMA ASCII
B255 A6 6B   		LDX	TEMP1		; WHERE TO STORE
B257 9D 1F 0D		STA	MESAGE,X
B25A A9 3C   		LDA	#60		; END OF LINE
B25C 85 CF   		STA	MESTIM		; WAIT 1 SECOND
B25E 60      		RTS
B25F         	LDMES6
B25F C9 FD   		CMP	#$FD		; RANK ?
B261 D0 05   		BNE	LDMS12		; NO
B263 A4 CD   		LDY	ENDRAT
B265 B9 E9 BE		LDA	RANKTAB,Y		; RANK WORD
B268         	LDMS12
B268 85 6C   		STA	TEMP2		; STORE FOR BITS 7,6
B26A 29 3F   		AND	#$3F
B26C 85 6A   		STA	TEMP		; WORD LOC IN #WRDTAB
B26E A9 2A   		LDA	#WRDTAB-1
B270 85 68   		STA	PNTR
B272 A9 BC   		LDA	#WRDTAB-1/256
B274 85 69   		STA	PNTR+1		; WHERE TO START SEARCH
B276         	LDMES7
B276 E6 68   		INC	PNTR		; ADVANCE WORD POINTER
B278 D0 02   		BNE	LDMES8
B27A E6 69   		INC	PNTR+1
B27C         	LDMES8
B27C A0 00   		LDY	#$00
B27E B1 68   		LDA	(PNTR),Y
B280 10 F4   		BPL	LDMES7		; NOT START OF A WORD
B282 C6 6A   		DEC	TEMP		; IS IT THE RIGHT WORD?
B284 D0 F0   		BNE	LDMES7		; NO
B286         	LDMES9
B286 29 3F   		AND	#$3F		; REMOVE ANY FLAG BITS
B288 49 A0   		EOR	#$A0		; PLAYFIELD AND DMA ASCII
B28A A6 6B   		LDX	TEMP1		; DISPLAY POINTER
B28C E6 6B   		INC	TEMP1		; ADVANCE DISPLAY POINTER
B28E 9D 1F 0D		STA	MESAGE,X
B291 C8      		INY			; NEXT LETTER
B292 B1 68   		LDA	(PNTR),Y	; A=LETTER
B294 10 F0   		BPL	LDMES9
B296 E6 6B   		INC	TEMP1		; A SPACE
             	;		END OF WORD FOUND
B298 A9 3C   		LDA	#60		; WAIT 1 SECOND
B29A 24 6C   		BIT	TEMP2		; WHAT TO DO NEXT
B29C 10 04   		BPL	LDMS11		; NOT END OF LINE
B29E 50 08   		BVC	LDMS10		; END OF LINE ONLY
B2A0 A9 FE   		LDA	#FE		; WAIT 4 SECOND, END OF SENTENCE
B2A2         	LDMS11
B2A2 50 96   		BVC	LDMES4		; CONTINUE WITH LINE
B2A4 A0 FF   		LDY	#$FF		; END OF SENTENCE
B2A6 84 D1   		STY	SENPTR
B2A8         	LDMS10
B228 85 CF   		STA	MESTIM		; STORE WAIT
B2AA 60      		RTS
             	;
             	;
             	;
             	;
             	;
B2AB         	AUDIO
             	;		AUDIO SERVICE ROUTINE
             	;
             	;		CH4 NOTE SECTION
B2AB A5 D6   		LDA	NPRIOR
B2AD F0 37   		BEQ	AUDIO1
B2AF C6 D8   		DEC	NDURTM		; TIMING OUT ?
B2B1 10 33   		BPL	AUDIO1		; YES
B2B3 A5 D9   		LDA	NOTVOL
B2B5 F0 0A   		BEQ	AUDIO2		; NEXT NOTE
B2B7 A5 D5   		LDA	SDURAT		; SPACE BETWEEN NOTE
B2B9 30 06   		BMI	AUDIO2
B2BB 85 D8   		STA	NDURTIM
B2BD A0 00   		LDY	#$00
B2BF F0 20   		BEQ	AUDIO3		; JUMP
B2C1         	AUDIO2
B2C1 A5 D4   		LDA	NDURAT
B2C3 85 D8   		STA	NDURTM
B2C5 A6 D2   		LDX	NOTSEQ
B2C7 E6 D2   		INC	NOTSEQ
B2C9 BD 5C BF		LDA	NOTTAB,X
B2CC 8D 06 D2		STA	AUDF4
B2CF A0 A8   		LDY	#$A8
B2D1 C9 FF   		CMP	#$FF
B2D3 D0 0C   		BNE	AUDIO3
B2D5 A5 D7   		LDA	REPPTR
B2D7 85 D2   		STA	NOTSEQ
B2D9 C6 D3   		DEC	REPSEQ
B2DB 10 E4   		BPL	AUDIO2
B2DD A0 00   		LDY	#$00
B2DF 84 D6   		STY	NPRIOR
B2E1         	AUDIO3
B2E1 8C 07 D2		STY	AUDC4
B2E4 84 D9   		STY	NOTVOL
B2E6         	AUDIO1
B2E6 A5 E2   		LDA	EXPDEL		; ZYLON HIT SERVICE
B2E8 F0 09   		BEQ	AUD11
B2EA C6 E2   		DEC	EXPDEL
B2EC D0 05   		BNE	AUD11
B2EE A2 14   		LDX	#NOITB2-NOISTB
B2F0 20 A8 AE		JSR	NOISE
B2F3         	AUD11
B2FE A6 70   		LDX	SPEED
B2F5 8A      		TXA
B2F6 4A      		LSR	A
B2F7 4A      		LSR	A
B2F8 4A      		LSR	A
B2F9 4A      		LSR	A
B2FA 4A      		LSR	A
B2FB C5 E1   		CMP	AUDTIM
B2FD 90 2C   		BCC	AUDIO
B2FF A9 00   		LDA	#$00
B301 85 E1   		STA	AUDTIM
             	;			ENGINES
B303 E8      		INX
B304 8A      		TAX
B305 49 FF   		EOR	#$FF
B307 8D 04 D2		STA	AUDF3
B30A AA      		TAX
B30B 0A      		ASL	A
B30C 0A      		ASL	A
B30D 0A      		ASL	A
B30E 0A      		ASL	A
B30F 0A      		ASL	A
B310 8D 00 D2		STA	AUDF1
B313 8A      		TXA
B314 4A      		LSR	A
B315 4A      		LSR	A
B316 4A      		LSR	A
B317 8D 02 D2		STA	AUDF2
B31A 4A      		LSR	A
B31B 49 8F   		EOR	#$8F
B31D 8D 03 D2		STA	AUDC2
B320 29 87   		AND	#$87
B322 8D 05 D2		STA	AUDC3
B325 A9 70   		LDA	#$70
B327 8D 08 D2		STA	AUDCTL
B32A 60      		RTS
B32B         	AUD10
B32B A5 DB   		LDA	AUDEXP		; EXPLOSION SERVICE
B32D F0 08   		BEQ	AUDIO4
B32F C6 DB   		DEC	AUDEXP
B331 D0 04   		BNE	AUDIO4
B333 A9 8F   		LDA	#$8F
B335 85 DC   		STA	ATYPE2
B337         	AUDIO4
B337 A6 DA   		LDX	PHOREP
B339 F0 1C   		BEQ	AUDIO5
B33B C6 DA   		DEC	PHREP
B33D D0 0A   		BNE	AUD12
B33F A9 AF   		LDA	#$AF
B341 85 DC   		STA	ATYPE2
B343 A9 02   		LDA	#$02
B345 85 DE   		STA	AFREQ1
B347 85 DF   		STA	AFREQ2
B349         	AUDI12
B349 BD EA BF		LDA	PHOTB2-1,X
B34C 85 DD   		STA	ATYPE3
B34E BD F2 BF		LDA	PHOTB4-1,X
B351 8D 04 D2		STA	AUDF3
B354 8D 09 D2		STA	STIMER
B357         	AUDIO5
B357 A5 E3   		LDA	BIGEXP		; FINAL EXPLOS SERVICE
B359 F0 0E   		BEQ	AUDIO6
B35B C6 E3   		DEC	BIGEXP
B35D AD 0A D2		LDA	RANDOM
B360 8D 04 D2		STA	AUDF3
B363 29 20   		AND	#$20
B365 45 DD   		EOR	ATYPE3
B367 85 DD   		STA	ATYPE3
B369         	AUDIO6
B369 18      		CLC		; SWEEP DOWN CH1-2
B36A A5 DE   		LDA	AFREQ1
B36C 65 E0   		ADC	AUDADD
B36E 85 DE   		STA	AFREQ1
B370 8D 00 D2		STA	AUDF1
B373 A5 DF   		LDA	AFREQ2
B375 69 00   		ADC	#$00
B377 85 DF   		STA	AFREQ2
B379 8D 02 D2		STA	AUDF2
             	;			VOLUME CONTROL
B37C A6 DC   		LDX	ATYPE2
B37E A4 DD   		LDY	ATYPE3
B380 A5 72   		LDA	TIMERX
B382 4A      		LSR	A
B383 90 1A   		BCC	AUDIO7
B385 A5 E1   		LDA	AUDTIM
B387 F0 16   		BEQ	AUDIO7
B389 C6 E1   		DEC	AUDTIM
B38B C9 11   		CMP	#$11
B38D B0 10   		BCS	AUDIO7
B38F 8A      		TXA
B390 29 0F   		AND	#$0F
B392 F0 03   		BEQ	AUDIO8
B394 CA      		DEX
B395 86 DC   		STX	ATYPE2
B397         	AUDIO8
B397 98      		TYA
B398 29 0F   		AND	#$0F
B39A F0 03   		BEQ	AUDIO7
B39C 88      		DEY
B39D 84 DD   		STY	ATYPE3
B39F         	AUDIO7
B39F 8E 03 D2		STX	AUDC2
B3A2 8C 05 D2		STY	AUDC3
B3A5 60      		RTS
             	;
             	;
             	;
B3A6         	NOTINT
             	;		AUDIO  NOTE INIT, X=CH4TAB PNTR
B3A6 BD 3E BF		LDA	CH4TAB,X
B3A9 C5 D6   		CMP	NPRIOR
B3AB 90 0C   		BCC	NOTIN2
B3AD A0 05   		LDY	#$05
B3AF         	NOTIN1
B3AF BD 3E BF		LDA	CH4TAB,X
B3B2 99 D2 00		STA	NOTSEQ,Y
B3B5 E8      		INX
B3B6 88      		DEY
B3B7 10 F6   		BPL	NOTIN1
B3B9         	NOTIN2
B3B9 60      		RTS

             	;
             	;
             	;
             	;
             	;
B3BA         	LDTABS
             	;		INIT PTAB,BCDCON,VCONL,VCONH,DISCTL,CHTRAM
             	;
B3BA A2 59   		LDX	#89
B3BC         	LDTB10
B3BC A9 0D   		LDA	#$0D
B3BE 9D 85 02		STA	DISPLY+5,X
B3C1 E0 0A   		CPX	#$0A
B3BC B0 05   		BCS	LDTAB8
             	;		LD PF COLORS
B3C5 BD A9 BF		LDA	CLITAB,X
B3C8 95 F2   		STA	COLRAM+4,X
B3CA         	LDTAB8
B3CA CA      		DEX
B3CB 10 EF   		BPL	LDTB10
B3CD A9 70   		LDA	#$70
B3CF 8D 80 02		STA	DISPLY+0
B3D2 8D 81 02		STA	DISPLY+1
B3D5 A9 41   		LDA	#$41
B3D7 8D E7 02		STA	DISPLY+103
B3DA A9 80   		LDA	#DISPLY
B3DC 8D E8 02		STA	DISPLY+104
B3DF A9 02   		LDA	#DISPLY/256
B3E1 8D E9 02		STA	DISPLY+105
             	;
             	;
             	;
             	;
             	;
B3E4 A2 00   		LDX	#$00
B3E6 86 68   		STX	PNTR
B3E8 86 69   		STX	PNTR+1
B3EA 86 6A   		STX	TEMP
B3EC 86 6B   		STX	TEMP1
B3EE         	LDTAB1
B3EE 18      		CLC
B3EF A5 68   		LDA	PNTR
B3F1 69 51   		ADC	#SCPTAB
B3F3 85 68   		STA	PNTR
B3F5 A5 69   		LDA	PNTR+1
B3F7 9D E9 0D		STA	PTAB,X
B3FA 69 00   		ADC	#$00
B3FC 85 69   		STA	PNTR+1
B3FE 18      		CLC
B3FF A5 6A   		LDA	TEMP
B401 69 6A   		ADC	#SCBCD
B403 85 6B   		STA	TEMP
B405 A5 6B   		LDA	TEMP1
B407 9D E9 0E		STA	BCDCON,X
B40A F8      		SED
B40B 69 00   		ADC	#$00
B40D D8      		CLD
B40E 85 6B   		STA	TEMP1
B410 E8      		INX
B411 D0 DB   		BNE	LDTAB1
             	;
B413 A2 00   		LDX	#$00
B415 86 68   		STX	PNTR
B417 A9 10   		LDA	#MEMMAP/256
B419 85 69   		STA	PNTR+1
B41B         	LDTAB2
B41B 18      		CLC
B41C A5 68   		LDA	PNTR
B41E 9D 00 08		STA	VCONL,X
B421 69 28   		ADC	#SCVCON
B423 85 68   		STA	PNTR
B425 A5 69   		LDA	PNTR+1
B427 9D 64 08		STA	VCONH,X
B42A 69 00   		ADC	#$00
B42C 85 69   		STA	PNTR+1
B42E BD 42 BB		LDA	STINIT,X
B431 9D 49 09		STA	DISCTL,X
B434 E8      		INX
B435 E0 64   		CPX	#100
B437 90 E2   		BCC	LDTAB2
B439 CA      		DEX		; X=99, DONT JUMP IMMEDIATELY
B43A 86 78   		STX	JMPTIM
             	;
B43C A2 03   		LDX	#$03
B43E 8E 11 09		STX	CHTRAM+72	; NOTHING IN SHIPS INIT QUAD
B441         	LDTAB3
B441 BD A6 BB		LDA	CHRTAB,X
B444 85 6A   		STA	TEMP
B446 A4 62   		LDY	MISDIF
B448 C8      		INY
B449 C8      		INY
B44A 84 6B   		STY	TEMP 1
B44C         	LDTAB4
B44C AD 0A D2		LDA	RANDOM
A44F 29 7F   		AND	#$7F
B451 A8      		TAY
B452 B9 C9 08		LDA	CHTRAM,Y
B455 D0 F5   		BNE	LDTAB4
B457 A5 6A   		LDA	TEMP
             		;		STARBASES NOT ON EDGES
B459 10 21   		BPL	LDTAB7
B45B C0 10   		CPY	#$10
B45D 90 ED   		BCC	LDTAB4
B45F C0 70   		CPY	#$70
B461 B0 E9   		BCS	LDTAB4
B463 98      		TYA
B464 29 0F   		AND	#$0F
B466 F0 E4   		BEQ	LDTAB4
B468 C9 0F   		CMP	#$0F
B46A F0 E0   		BEQ	LDTAB4
B46C B9 C8 08		LDA	CHTRAM-1,Y
B46F 19 CA 08		ORA	CHTRAM+1,Y
B472 19 D9 08		ORA	CHTRAM+16,Y
B475 19 B9 08		ORA	CHTRAM-16,Y
B478 D0 D2   		BNE	LDTAB4
B47A A5 6A   		LDA	TEMP
B47C         	LDTAB7
B47C 99 C9 08		STA	CHTRAM,Y
B47F C6 6B   		DEC	TEMP1
B481 10 C9   		BPL	LDTAB4
B483 CA      		DEX
B484 10 BB   		BPL	LDTAB3
             	;		LOAD HORIZ WALL OF CHART
B486 A2 B4   		LDX	#180
B488         	LDTAB5
B488 A9 0A   		LDA	#$0A
B48A 9D 34 0D		STA	CHTDIS-1,X
B48D CA      		DEX
B48E D0 F8   		BNE	LDTAB5
B490 A2 0F   		LDX	#$0F		; LD HORIZ LINE
B492         	LDTAB6
B492 A9 18   		LDA	#$18
B494 9D 37 0D		STA	CHTDIS+2,X
B497 CA      		DEX
B498 10 F8   		BPL	LDTAB6
             	;
B49A A9 1A   		LDA	#$1A		; FILL IN THE DOT ON THE CHART
B49C 8D 47 0D		STA	CHTDIS+18
             	;
B49F A9 00   		LDA	#$00
B4A1 8D 11 09		STA	CHTRAM+72
B4A4 A9 48   		LDA	#72
B4A6 85 90   		STA	QUADRT
B4A8 A9 43   		LDA	#67
B4AA 85 8D   		STA	GHPOS
B4AC 85 8F   		STA	HYHPOS
B4AE A9 47   		LDA	#$47
B4B0 85 8E   		STA	HYVPOS
B4B2 85 8C   		STA	GVPOS
B4B4 A9 EA   		LDA	#$EA
B4B6 8D E8 0F		STA	BCDCON+255		; INFIINITY SIGN
             	;
             	;		FALL THROUGH TO LDGALT
             	;
B4B9         	LDGALT
             	;
             	;		LD UP THE GALACTIC CHART
             	;		TRANSFER CHTRAM TO CHTDIS
             	;
B4B9 A0 00   		LDY	#$00		; CHTDIS PNTR
B4BB 84 6A   		STY	TEMP		; CHTRAM PNTR
B4BD         	LDGAL1
B4BD A6 6A   		LDX	TEMP
B4BF BD C9 08		LDA	CHTRAM,X		; WHATS IN QUAD
B4C2 10 02   		BPL	LDGAL2		; NO
B4C4 A9 05   		LDA	#$05		; STARBASE DEFAULT
B4C6         	LDGAL2
B4C6 AA      		TAX
B4C7 BD D1 BE		LDA	CHTABL,X		; CODE FOR CHTDIS
B4CA 99 4B 0D		STA	CHTDIS+22,Y
B4CD C8      		INY
B4CE E6 6A   		INC	TEMP
B4D0 A5 6A   		LDA	TEMP
B4D2 29 0F   		AND	#$0F		; END OF LINE ?
B4D4 D0 E7   		BNE	LDGAL1		; NO
B4D6 A9 19   		LDA	#$19		; VERT LINE
B4D8 99 4B 0D		STA	CHTDIS+22,Y
B4DB C8      		INY
B4DC C8      		INY
B4DD C8      		INY		; ADVANCE TO NEXT LINE
B4DE C8      		INY
B4DF C0 A0   		CPY	#160		; ALL DONE ?
B4E1 90 DA   		BCC	LDGAL1		; NO
B4E3 60      		RTS
             	;
             	;
             	;
             	;
B4E4         	TIMERS
             	;		SERVICE TIMERS, STARDATE AND ZYLON JUMP
             	;	UPDATE TIMEX, USED FOR STAR INTENSITY MULTIPLEX
             	;
B4E4 E6 76   		INC	BINTIM		; UPDATE BINARY TIMER
B4E6 A2 90   		LDX	#DIMBLU
B4E8 A5 76   		LDA	BINTIM
B4EA 10 09   		BPL	TIME46
B4EC AC 55 09		LDY	DENERG+0
B4EF C0 80   		CPY	#$80
B4F1 D0 02   		BNE	TIME46
B4F3 A2 44   		LDX	#RED
B4F5         	TIME46
B4F5 29 03   		AND	#$03
B4F7 85 72   		STA	TIMERX
B4F9 D0 1F   		BNE	TIME33
             	;	SHIELDS SECTION
B4FB A4 7D   		LDY	SHENER
B4FD F0 17   		BEQ	TIME31
B4FF A0 A0   		LDY	#DBLUE
B501 2C 94 09		BIT	DAMAGE+2
B504 10 0B   		BPL	TIME47
B506 70 07   		BVS	TIME32
B508 AD 0A D2		LDA	RANDOM
B50B C9 C8   		CMP	#200
B50D 90 07   		BCC	TIME31
B50F         	TIME32
B50F A0 00   		LDY	#$00
B511         	TIME47
B511 98      		TYA
B512 D0 02   		BNE	TIME31
B514 A2 26   		LDX	#YELLOW
B516         	TIME31
B516 84 81   		STY	SPABAK
B518 86 FB   		STX	COLRAM+13
B51A         	TIME33
             	;		END UPDATE TIMERX
             	;
             	;		PHOTON TIMEOUT
B51A A2 02   		LDX	#402
B51C         	TIMER6
B51C BD 8E 0C		LDA	GINDEX+2,X		; PHOTON ?
B51F D0 06   		BNE	TIMER7
B521 B5 EB   		LDA	STFLAG+2,X		; PHOTON TIMEOUT ?
B523 F0 02   		BEQ	TIMER7		; YES
B525 D6 EB   		DEC	STFLAG+2,X		; DEC PHOTON TIMER
B527         	TIMER7
B527 CA      		DEX
B528 10 F2   		BPL	TIMER6
             	;
             	;		EXPLOSION TIMEOUT
             	;
B52A A5 73   		LDA	ETIMER
B52C F0 16   		BEQ	TIME10
B52E C6 73   		DEC	ETIMER
B530 D0 04   		BNE	TIMER9
B532 A2 11   		LDX	#STLAST+1		; 1 FOR FALL THROUGH
B534 86 79   		STX	NSTARS
B536         	TIMER9
B536 C9 70   		CMP	#$70
B538 B0 04   		BCS	TIME30
B53A A2 00   		LDX	#$00
B53C 86 8A   		STX	HITME
B53E         	TIME30
B53E C9 18   		CMP	#$18
B540 B0 02   		BCS	TIME10
B542 C6 79   		DEC	NSTARS
B544         	TIME10
B544 C6 74   		DEC	SECOND
B546 10 21   		BPL	TIMER1
B548 A9 28   		LDA	#$28
B54A 85 74   		STA	SECOND
B54C A2 04   		LDX	#$04
B54E         	TIMER2
B54E FE A3 09		INC	DSDATE,X
B551 BD A3 09		LDA	DSDATE,X
B554 C9 DA   		CMP	#$DA
B556 90 0D   		BCC	TIMER3
B558 A9 D0   		LDA	#$D0
B55A 9D A3 09			   STA	DSDATE,X
B55D E0 03   		CPX	#$03
B55F D0 01   		BNE	TIMER4
B561 CA      		DEX
B562         	TIMER4
B562 CA      		DEX
B563 10 E9   		BPL	TIMER2
B565         	TIMER3
B565 C6 78   		DEC	JMPTIM
B567 30 01   		BMI	TIMER5
B569         	TIMER1
B569 60      		RTS
B56A         	TIMER5
B56A A9 31   		LDA	#49
B56C 85 78   		STA	JMPTIM
             	;		RATING DUE TO TIME
B56E A5 CB   		LDA	RATING
B570 D0 02   		BNE	TIME61
B572 C6 CC   		DEC	RATING+1
B574         	TIME61
B574 C6 CB   		DEC	RATING
B576 A6 64   		LDX	ATRACT		; GAME OVER ?
B578 D0 EF   		BNE	TIMER1		; YES
             	;			ZYLONS JUMP
             		; CHECK ALL STARBASES TO SEE IF DESTROYED
             		; X=0 FROM ABOVE
B57A 86 6A   		STX	TEMP
B57C         	TIME12
B57C BD C9 08		LDA	CHTRAM,X		; STARBASE ?
B57F 10 19   		BPL	TIME11			; NO
B581 20 F1 B7		JSR	TIMHLP
B584 F0 14   		BEQ	TIME11
             	;			STARBASE DESTROUED
B586 A9 02   		LDA	#$02		; 4 ZYLONS
B588 9D C9 08		STA	CHTRAM,X
B58B 85 6A   		STA	TEMP
B58D 38      		SEC
B58E A5 CB   		LDA	RATING
B590 E9 12   		SBC	#18
B592 85 CB   		STA	RATING
B594 A5 CC   		LDA	RATING+1
B596 E9 00   		SBC	#$00
B598 85 CC   		STA	RATING+1
             	;
B59A         	TIME11
B59A E8      		INX
B59B 10 DF   		BPL	TIME12
B59D A5 6A   		LDA	TEMP		; ANY STARBASES DESTROYED ?
B59F F0 0F   		BEQ	TIME13		; NO
B5A1 C2 97 09		BIT	DAMAGE+5		; COMMUNICATIONS
B5A4 70 0A   		BVS	TIME13
B5A6 A0 15   		LDY	#SENDES-SENTAB
B5A8 20 23 B2		JSR	LDMESS
B5AB A2 18   		LDX	#CH4TB5-CH4TAB		; MESSAGE
B5AD 20 A6 B3		JSR	NOTINT
B5B0         	TIME13
B5B0 C6 9F   		DEC	JMPOUT		; JUMP TIMEOUT
B5B2 30 07   		BMI	TIME28
B5B4 A6 93   		LDX	KILBAS
B5B6 BD C9 08		LDA	CHTRAM,X		; NEED A NEW BASE ?
B5B9 30 1F   		BMI	TIME14		; NO
B5BB         	TIME28
B5BB A9 07   		LDA	#$07		; JUMP TIMEOUT RESTORED
B5BD 85 9F   		STA	JMPOUT
B5BF A0 7F   		LDY	#127
B5C1         	TIME15
B5C1 AD 0A D2		LDA	RANDOM
B5C4 29 7F   		AND	#$7F
B5C6 AA      		TAX
B5C7 BD C9 08		LDA	CHTRAM,X
B5CA 30 0E   		BMI	TIME14		; NEW BASE
B5CC 88      		DEY
B5CD 10 F2   		BPL	TIME15		; TRY AGAIN
B5CF A2 7F   		LDX	#127
B5D1         	TIME16
B5D1 BD C9 08		LDA	CHTRAM,X
B5D4 30 04   		BMI	TIME14
B5D6 CA      		DEX
B5D7 10 FB   		BPL	TIME16
B5D9 60      		RTS
             	;
B5DA         	TIME14
B5DA 86 93   		STX	KILBAS		; STORE STXRBASE
B5DC 8A      		TXA
B5DD 29 0F   		AND	#$0F
B5DF 85 94   		STA	KILOCH
B5E1 8A      		TXA
B5E2 4A      		LSR	A
B5E3 4A      		LSR	A
B5E4 4A      		LSR	A
B5E5 4A      		LSR	A
B5E6 85 95   		STA	KILOCV
B5E8 A2 FF   		LDX	#$FF
B5EA         	TIME18			; MAIN LOOP
B5EA E8      		INX
B5EB 10 30   		BPL	TIME40
             	;		END ZYLON JUMP ROUTINE
B5ED A2 00   		LDX	#$00
B5EF         	TIME20
B5EF BD C9 08		LDA	CHTRAM,X
B5F2 29 DF   		AND	#$DF
B5F4 9D C9 08		STA	SHTRAM,X
B5F7 E8      		INX
B5F8 10 F5   		BPL	TIME20
B5FA 2C 97 09		BIT	DAMAGE+5
B5ED 70 1D   		BVS	TIME44
B5FF A2 00   		LDX	#$00		; ANY STARBASES SURROUNDED ?
B601         	TIME21
B601 BD C9 08		LDA	CHTRAM,X
B604 10 13   		BPL	TIME19
B606 20 F1 B7		JSR	TIMHLP
B609 F0 0E   		BEQ	TIME19
             	;		STAR	BASE SURROUNDED
B60B A9 63   		LDA	#99
B60D 85 78   		STA	JMPTIM		; 99 CENTONS BEFORE DESTROY
B60F A0 13   		LDY	#SENSUR-SENTAB
B611 20 23 B2		JSR	LDMESS
B614 A2 18   		LDX	#CH4TB5-CH4TAB
B616 4C A6 B3		JMP	NOTINT
B619         	TIME19
B619 E8      		INX
B61A 10 E5   		BPL	TIME21
B61C         	TIME44
B61C 60      		RTS
B61D         	TIME40
B61D BC C9 08		LDY	CHTRAM,X
B620 C0 0A   		CPY	#$0A		; STARBASE , OR ALREADY CALCULATED
B622 B0 C6   		BCS	TIME18
B624 AD 0A D2		LDA	RANDOM
B627 D9 BB BF		CMP	JMPWHN,Y
B62A B0 BE   		BCS	TIME18
B62C E4 90   		CPX	QUADRT
B62E F0 BA   		BEQ	TIME18
             	;		CALCULATE GRADIENT
B630 A0 08   		LDY	#$08
B632         	TIME27
B632 18      		CLC
B633 8A      		TXA
B634 79 C0 BF		ADC	JMPTAB,Y
B637 B5 6A   		STA	TEMP
B639 29 0F   		AND	#$0F
B63B 38      		SEC
B63C E5 94   		SBC	KILOCH
B63E B0 04   		BCS	TIME26
B640 49 FF   		EOR	#$FF
B642 69 01   		ADC	#$01
B644         	TIME26
B644 85 6B   		STA	TEMP1
B646 A5 6A   		LDA	TEMP
B648 4A      		LSR	A
B649 4A      		LSR	A
B64A 4A      		LSR	A
B64B 4A      		LSR	A
B64C 38      		SEC
B64D E5 95   		SBC	KILOCV
B64F B0 04   		BCS	TIME22
B651 49 FF   		EOR	#$FF
B653 69 01   		ADC	#$01
B655         	TIME22
B655 18      		CLC
B656 65 6B   		ADC	TEMP1
B658 99 96 00		STA	JMPPTS,Y
B65B 88      		DEY
B65C 10 D4   		BPL	TIME27
             	;		ZYLON CONVERGENCE
B65E A9 01   		LDA	#$01
B660 85 6B   		STA	TEMP1
B662         	TIME23
B662 A0 07   		LDY	#$07
B664         	TIME24
B664 B9 96 00		LDA	JMPPTS,Y
B667 C5 9E   		CMP	JMPPTS+8
B669 B0 24   		BCS	TIME42
B66B 18      		CLC
B66C 8A      		TXA
B66D 79 C0 BF		ADC	JMPTAB,Y
B670 30 1D   		BMI	TIME42
B672 84 6A   		STY	TEMP
B674 A8      		TAY
B675 B9 C9 08		LDA	CHTRAM,Y
B678 D0 13   		BNE	TIME25
B67A BD C9 08		LDA	CHTRAM,X
B67D C4 90   		CPY	QUADRT
B67F F0 0C   		BEQ	TIME25
B681 09 20   		ORA	#$20
B683 99 C9 08		STA	CHTRAM,Y
B686 A9 00   		LDA	#$00
B688 9D C9 08		STA	CHTRAM,X
B68B F0 0B   		BEQ	TIME45
B68D         	TIME25
B68D A4 6A   		LDY	TEMP
B68F         	TIME42
B68F 88      		DEY
B690 10 D2   		BPL	TIME24
B692 E6 9E   		INC	JUMPPTS+8
B694 C6 6B   		DEC	TEMP1
B696 10 CA   		BPL	TIME23
B698         	TIME45
B698 4C EA B5		JMP	TIME18
             	;
             	;
             	;
B69B         	ROHELP
             	;	HELPER SUB FOR YROTAT, ZROTAT
B69B BD AD 09		LDA	XSIGN,X
B69E 49 01   		EOR	#$01
B6A0 F0 02   		BEQ	ROHLP1
B6A2 A9 FF   		LDA	#$FF
B6A4         	ROHLP1
B6A4 85 6B   		STA	TEMP1
B6A6 85 6C   		STA	TEMP2
B6A8 BD 40 0A		LDA	XPOSH,X
B6AB 85 6A   		STA	TEMP
B6AD AD 0A D2		LDA	RANDOM
B6B0 09 BF   		ORA	#$BF
B6B2 5D D3 0A		EOR	XPOSL,X
B6B5 0A      		ASL	A
B6B6 26 6A   		ROL	TEMP
B6B8 26 6B   		ROL	TEMP1
B6BA 0A      		ASL	A
B6BB 26 6A   		ROL	TEMP
B6BD 26 6B   		ROL	TEMP1
             	;
B6BF A5 6D   		LDA	TEMP3		; JOYSTICK
B6C1 49 FF   		EOR	#$FF		; TOGGLES EVERY TIME THROUGH, CALL TWICE/STAR
B6C3 85 6D   		STA	TEMP3		; THEN OK, THIS CAN BE TRICKY SO WATCH OUT !!
             	;
B6C5 30 1A   		BMI	ROHLP2
B6C7 18      		CLC
B6C8 B9 D3 0A		LDA	XPOSL,Y
B6CB 65 6A   		ADC	TEMP
B6CD 99 D3 0A		STA	XPOSL,Y
B6D0 B9 40 0A		LDA	XSIGN,Y
B6D3 65 6A   		ASC	TEMP
B6CD 99 D3 0A		STA	XPOSL,Y
B6D0 B9 40 0A		LDA	XSIGN,Y
B6D3 65 6B   		ADC	TEMP1
B6D5 99 40 0A		STA	XPOSH,Y
B6D8 B9 AD 09		LDA	XSIGN,Y
B6DB 65 6C   		ADC	TEMP2
B6DD 99 AD 09		STA	XSIGN,Y
B6E0 60      		RTS
B6E1         	ROHLP2
B6E1 38      		SEC
B6E2 B9 D3 0A		LDA	XPOSL,Y
B6E5 E5 6A   		SBC	TEMP
B6E7 99 D3 0A		STA	XPOSL,Y
B6EA B9 40 0A		LDA	XPSH,Y
B6ED E5 6B   		SBC	TEMP1
B6EF 99 40 0A		STA	XPOSH,Y
B6F2 B9 AD 09		LDA	XSIGN,Y
B6F5 E5 6C   		SBC	TEMP2
B6F7 99 AD 09		STA	XSIGN,Y
B6FA 60      		RTS
             	;
             	;
             	;
B6FB         	STHPOS
             	;		STORE HPOS, X=STR INDEX
B6FB C9 50   		CMP	#HOFLOW
B6FD B0 5B   		BCS	STVPS1
B6FF 85 6D   		STA	TEMP3
B701 A9 50   		LDA	#HSTCEN
B703 E0 05   		CPX	#OBJNUM
B705 B0 02   		BCS	STHPS2
B707 A9 7D   		LDA	#HOBCEN
B709         	STHPS2
B709 BC DE 09		LDY	YSIGN,X
B70C D0 09   		BNE	STHPS3
B70E 38      		SEC
B70F E6 6D   		INC	TEMP3
B711 E6 6D   		SBC	TEMP3
B713 9D 2A 0C		STA	HPOS,X
B716 60      		RTS
B717         	STHPS3
B717 18      		CLC
B718 65 6D   		ADC	TEMP3
B71A 9D 2A 0C		STA	HPOS,X
B71D 60      		RTS
             	;
B71E         	S1VPOS
             	;		STORE VPOS, X=STAR INDEX
B71E C9 32   		CMP	#VOFLOW
B720 B0 38   		BCS	STVPS1
B722 85 6D   		STA	TEMP3
B724 A9 32   		LDA	#VSTCEN
B726 E0 05   		CPX	#OBJNUM
B728 B0 04   		BCS	STVPS2
B72A 06 6D   		ASL	TEMP3
B72C A9 7A   		LDA	#VOBCEN
B72E         	STVPS2
B72E 24 D0   		BIT	DISFLG		; SECTOR SCAN ?
B730 50 13   		BVC	STVPS5		; NO
B732 2C 96 09		BIT	DAMAGE+4
B735 10 07   		BPL	STVPS7
B737 2C 0A D2		BIT	RANDOM
B73A 50 0E   		BVC	STVPS6
B73E 70 15   		BVS	STVPS3
B73E         	STVPS7
B73E BC AD 09		LDY	XSIGN,X
B741 D0 07   		BNE	STVPS6
B743 F0 0E   		BEQ	STVPS3
B745         	STVPS5
B745 BC 0F 0A		LDY	ZSIGN,X
B748 F0 09   		BEQ	STVPS3
B74A         	STVPS6
B74A 38      		SEC
B74B E6 6D   		INC	TEMP3
B74D E5 6D   		SBC	TEMP3
B74F 9D F9 0B		STA	VPOS,X
B752 60      		RTS
B753         	STVPS3
B753 18      		CLC
B754 65 6D   		ADC	TEMP3
B756 9D F9 0B		STA	VPOS,X
B759 60      		RTS
B75A         	STVPS1		; ENTRY POINT FROM STHPOS  **************
B75A E0 05   		CPX	#OBJNUM
B75C B0 06   		BCS	STVPS4
B75E A9 FB   		LDA	#$FB
B760 9D F9 0B		STA	VPOS,X
B763         	STVPS8		; ENTRY POINT FROM NEWSTR  ***************
B763 60      		RTS
B764         	STVPS4
             	;
             	;		FALL THROUGH TO NEWSTR  ***************************
             	;
B674         	NEWSTR
             	;		NEW STAR POSITION
B764 A9 63   		LDA	#99		; RESET TO BOTTOM OF SCREEN
B766 9D F9 0B		STA	VPOS,X
B769 9D 2A 0C		STA	HPOS,X
B76C E0 11   		CPX	#STLAST+1		; EXPLOSION STARS
B76E B0 F3   		BCS	STVPS8		; YES
B770 AD 0A D2		LDA	RANDOM		; UPDATE Z
B773 29 0F   		AND	#$0F
B775 85 6A   		STA	TEMP
B777 9D A2 0A		STA	ZPOSH,X
B77A AD 0A D2		LDA	RANDOM		; UPDATE Y
B77D 29 0F   		AND	#$0F
B77F C5 6A   		CMP	TEMP
B781 90 02   		BCC	NEWST3
B783 85 6A   		STA	TEMP
B785         	NEWST3
B785 9D 71 0A		STA	YPOSH,X
             	;
B788 A9 0F   		LDA	#$0F
B78A 9D 40 0A		STA	XPOSH,X
B78D A5 D0   		LDA	DISFLG		; UPDATE X
B78F 49 01   		EOR	#$01
B791 29 01   		AND	#$01
B793 9D AD 09		STA	XSIGN,X
B796 D0 11   		BNE	NEWST5
B798 9D 04 0B		STA	YPOSL,X
B79B 9D 35 0B		STA	ZPOSL,X
B79E 38      		SEC
B79F E5 6A   		SBC	TEMP
B7A1 9D 40 0A		STA	XPOSH,X
             	;		TRY THIS FIX,  BELOW
B7A4 A9 80   		LDA	#$80
B7A6 9D D3 0A		STA	XPOSL,X
             	;
B7A9         	NEWST5
             	;
B7A9 24 D0   		BIT	DISFLG		; SECTOR SCAN ?
B7AB 50 11   		BVC	NEWST2		; NO
B7AD AD 0A D2		LDA	RANDOM
B7B0 9D 71 0A		STA	YPOSH,X
B7B3 AD 0A D2		LDA	RANDOM
B7B6 9D 40 0A		STA	XPOSH,X
B7B9 29 01   		AND	#$01
B7BB 9D AD 09		STA	XSIGN,X
B7BE         	NEWST2
             	;
B7BE         	NEWST4		; ENTRY POINT FROM HLINES SUB   *****************
             	;		DETERMINE SIGN Y,Z
B7BE AD 0A D2		LDA	RANDOM
B7C1 29 01   		AND	#$01
B7C3 9D 0F 0A		STA	ZSIGN,X
B7C6 D0 0F   		BNE	NEWST1
B7C8 38      		SEC
B7C9 FD 35 0B		SBC	ZPOSL,X
B7CC 9D 35 0B		STA	ZPOSL,X
B7CF A9 00   		LDA	#$00
B7D1 FC A2 0A		SBC	ZPOSH,X
B7D4 9D A2 0A		STA	ZPOSH,X
B7D7         	NEWST1
B7D7 AD 0A D2		LDA	RANDOM
B7DA 29 01   		AND	#$01
B7DC 9D DE 09		STA	YSIGN,X
B7DF D0 0F   		BNE	NEWST6
B7E1 38      		SEC
B7E2 FD 04 0B		SBC	YPOSL,X
B7E5 9D 04 0B		STA	YPOSL,X
B7E8 A9 00   		LDA	#$00
B7EA FD 71 0A		SBC	YPOSH,X
B7ED 9D 71 0A		STA	YPOSH,X
B7F0         	NEWST6
B7F0 60      		RTS
             	;
             	;
             	;
             	;
B7F1         	TIMHLP
             	;		HELPER ROUTINE FOR TIMERS
B7F1 BD C8 08		LDA	CHTRAM-1,X
B7F4 F0 0D   		BEQ	TIMHP1
B7F6 BD CA 08		LDA	CHTRAM+1,X
B7F9 F0 08   		BEQ	TIMHP1
B7FB BD B9 08		LDA	CHTRAM-16,X
B7FE F0 03   		BEQ	TIMHP1
B800 BD D9 08		LDA	CHTRAM+16,X
B803         	TIMHP1
B803 60      		RTS
             	;
             	;
             	;
             	;
             	;
             	;
             	;
B804         	PANDIS
             	;		PANNEL DISPLAY ROUTINE
             	;		ONE ENTRY POINT AT PANDS6
             	;	UPDATE VELOCITY DISPLAY
B804 A6 70   		LDX	SPEED
B806 E4 71   		CPX	WARP
B808 F0 08   		BEQ	PANDS2
B80A 90 04   		BCC	PANDS3
B80C C6 70   		DEC	SPEED
B80E B0 12   		BCS	PANDS1
B810         	PANDS3
B810 E6 70   		INC	SPEED
B812         	PANDS2
B812 A5 C0   		LDA	HFLAG
B814 D0 0C   		BNE	PANDS1
B816 2C 93 09		BIT	DAMAGE+1
B819 10 07   		BPL	PANDS1
B81B A5 71   		LDA	WARP
B81D 2D 0A D2		AND	RANDOM
B820 85 70   		STA	SPEED
             	;
             	;
B822         	PANDS1				; ALL DONE VELOCITY DISPLAY
B822 A0 01   		LDY	#DVELOC-DISCTL-1
B824 20 CD B8		JSR	TWOCM3
B827 2C 95 09		BIT	DAMAGE+3		; COMPUTER DAMAGE
B82A 30 30   		BMI	PANDS4
             	;		UPDATE COORDINATES DISPLAY
B82C A9 31   		LDA	#RAMNUM		; DISPLAY Y COORD
B82E A0 17   		LDY	#DTHETA-DISCTL	; DISPLAY IN THETA
B830 20 A7 B8		JSR	TWOCOM		; UPDATE THETA
B833 A9 62   		LDA	#RAMNUM*2		; DISPLAY Z COORD
B835 A0 1D   		LDY	#DPHI-DISCTL		; DISPLAY IN PHI
B837 20 A7 B8		JSR	TWOCOM		; UPDATE PHI
B83A A9 00   		LDA	#$00		; DISPLAY X COORD
B83C A0 23   		LDY	#DRHO-DISCTL		; DISPLAY IN RHO
B83E 20 A7 B8		JSR	TWOCOM		; UPDATE RHO
             	;		LOW BYTE OF RHO
B841 AD 6E 09		LDA	DRHO+2		; PUT BLANK IN LSB IF INFINITE
B844 8D 6D 09		STA	DHRO+3
B847 C9 0A   		CMP	#$0A		; INFINITE ?
B849 B0 11   		BCS	PANDS4		; YES
B84B AE 5C 09		LDX	DCSTOR		; WHICH OBJ TRACKING
B84E BD D3 0A		LDA	XPOSL,X		; LOW BYTE
B851 4A      		LSR	A
B852 4A      		LSR	A
B853 4A      		LSR	A
B854 4A      		LSR	A
B855 AA      		TAX
B856 BD E9 0E		LDA	BCDCON,X		; CONVERT TO BCD
B859 8D 6F 09		STA	DRHO+3		; LSB UPDATED
B85C         	PANDS4				; ALL DONE COORD DISP
             	;				UPDATE ENERGY DISPLAY
             	;		UPDATE ENERGY DUE TO SHIELDS WARPS ATTACK COMPUTER
B85C 18      		CLC
B85D A5 7F   		LDA	ENFLAG		; LSRB OF ENERGY, DEC ENERGY WHEN CARRY
B85F 65 7D   		ADC	SHENER		; DRAIN FROM SHIELDS
B861 65 80   		ADC	WPENER		; DRAIN FROM WARP
B863 65 7E   		ADC	ATENER		; DRAIN FROM ATTACK COMPUTER
B865 69 01   		ADC	#$01		; LIFE SUPPORT
B867 C5 7F   		CMP	ENFLAG		; SET CARRY FLAG
B869 85 7F   		STA	ENFLAG
B86B B0 39   		BCS	PANDS5
             	;			DECRE ENERGY
B86D A2 03   		LDA	#$03		; DECRE BIT 3 OF ENERGY
B84F         	PANDS6		; ENTRY POINT TO DECRE ENERGY   *************************
B86F 24 64   		BIT	ATRACT		; GAME OVER ?
B871 70 33   		BVS	PANDS5		; YES
             	;	X MUST BE DEFINED = BIT TO DECRE FROM
B873 DE 55 09		DEC	DENERG,X
B876 BD 55 09		LDA	DENERG,X
B879 C9 80   		CMP	#$80		; CHECK IF BORROW
B87B B0 29   		BCS	PANDS5		; NO BORROW
B87D A9 89   		LDA	#$89
B87F 9D 55 09		STA	DENERG,X
B882 E0 02   		CPX	#$02
B884 D0 08   		BNE	PANDS7
B886 A5 CB   		LDA	RATING
B888 D0 02   		BNE	PANDS8
B88A C6 CC   		DEC	RATING+1
B88C         	PANDS8
B88C C6 CB   		DEC	RATING
B88E         	PANDS7
B88E CA      		DEX
B88F 10 DE   		BPL	PANDS6		; NEXT DIGIT
             	;			OUT OF ENERGY  !!
B891 A2 0A   		LDX	#$0A		; KEY F
B893 8A      		TXA
B894 A0 03   		LDY	#$03
B896         	PAND10
B896 99 55 09		STA	DENERG+0,Y
B899 88      		DEY
B89A 10 FA   		BPL	RAND10
B89C 20 45 B0		JSR	KEYS15
B89F A0 31   		LDY	#SENOUT-SENTAB
B8A1 A2 04   		LDX	#$04
B8A3 20 0A B1		JSR	CRATE
B8A6         	PANDS9
B8A6         	PANDS5
B8A6 60      		RTS
             	;
             	;

             	;
B8A7         	TWOCOM
             	;		TWOS OMPLEMENT AND CONVERT TO B CD HELPER ROUTINE
             	;	A=OFFSET(X,Y,Z), Y=WHERE TO STORE
B8A7 18      		CLC
B8A8 6D 5C 09		ADC	DCSTOR		; WHICH OBJ TRACKING
B8AB AA      		TAX
B8AC A9 10   		LDA	#$10		; + SIGN
B8AE 85 6A   		STA	TEMP
B8B0 BD AD 09		LDA	XSIGN,X		; SIGN OF OBJ
B8B3 4A      		LSR	A
B8B4 BD 40 0A		LDA	XPOSH,X
B8B7 B0 04   		BCS	TWOCM1
             	;		NEGATIVE VALUE, TWOS COMPLEMENT
B8B9 49 FF   		EOR	#$FF
B8BB C6 6A   		DEC	TEMP		; - SIGN
B8BD         	TWOCM1
B8BD AA      		TAX
B8BE A5 6A   		LDA	TEMP
B8C0 99 49 09		STA	DISCTL+0,Y		; STORE SIGN
             	;
             	;		NO INFINITY FOR THETA OR PHI
B8C3 98      		TYA
B8C4 29 10   		AND	#$10		; THETA OR PHI ?
B8C6 F0 05   		BEQ	TWOCM3		; NO
B8C8 E0 FF   		CPX	#$FF		; INFINITY ?
B8CA D0 01   		BNE	TWOCM3		; NO
B8CC CA      		DEX			; X=FE, NOT FF
             	;
             	;
B8CD         	TWOCM3			; ENTRY POINT TO LOAD ONLY **************
             	;
B8CD BD E9 0E		LDA	BCDCON,X		; BCD CONVERT
B8D0 AA      		TAX
B8D1 29 0F   		AND	#$0F
B8D3 99 4B 09		STA	DISCTL+2,Y		; LOW BYTE STOED
B8D6 8A      		TXA
B8D7 4A      		LSR	A
B8D8 4A      		LSR	A
B8D9 4A      		LSR	A
B8DA 4A      		LSR	A
B8DB 99 4A 09		STA	DISCTL+1,Y		; HIGHT BYTE STORED
B8DE 60      		RTS
             	;
             	;
             	;
             	;
             	;
             	;
             	;
             	;		TABLES;
B8DF         	CLINDX		; COLOR INDEX TABLE USED IN OBJCOL SUBROUTINE
B8DF 00 01 02		.BYTE	0,1,2,3,7
B8E2 03 07   	
             	;
             	;
B8E4         	PHGRAF		; PHOTON GRAPHIC
B8E4 00      		.BYTE	0
B8E5 18 3C 7E		.BYTE	$18,$3C,$7E,$7E,$76,$F7,$DF,$DF,$FF,$FF,$F7,$76,$7E,$7E,$3C,$18
B8E8 7E 76 F7	
B8EB DF DF FF	
B8EE FF F7 76	
B8F1 7E 7E 3C	
B8F4 18      	
B8F5         	PHGRF1
B8F5 10 38 76		.BYTE	$10,$38,$7C,$7C,$FE,$DE,$DA,$FA,$EE,$EE,$7C,$7C,$38,$10
B8F8 7C FE DE	
B8FB DA FA EE	
B8FE EE 7C 7C	
B901 38 10   	
B903         	PHGRF2
B903 18 3C 3C		.BYTE	$18,$3C,$3C,$7E,$6E,$7A,$7E,$76,$7E,$3C,$3C,$18
B906 7E 6E 7A	
B909 7E 76 7E	
B90C 3C 3C 18	
B90F         	PHGRF3
B90F 10 38 38		.BYTE	$10,$38,$38,$7C,$74,$7C,$6C,$38,$38,$10
B912 7C 74 7C	
B915 6C 38 38	
B918 10      	
B919         	PHGRF4
B919 10 18 3C		.BYTE	$10,$18,$3C,$2C,$3C,$3C,$18,$08
B91C 2C 3C 3C	
B91F 18 08   	
B921         	PHGRF5
B921 10 38 38		.BYTE	$10,$38,$38,$28,$38,$10
B924 28 38 10
             	;
B927         	DKGRAF		; DOCKING SHIP GRAPHIC
B927 3C 3C 24		.BYTE	$3C,$3C,$24,$3C,$7E,$7E,$7E,$5A,$FF,$FF,$42,$42,$42,$42,$42,$42
B92A 3C 7E 7E	
B92D 7E 5A FF	
B930 FF 42 42	
B933 42 42 42	
B936 42      	
B937         	DKGRF1
B937 1C 1C 14		.BYTE	$1C,$1C,$14,$3E,$3E,$3E,$2A,$7F,$7F,$22,$22,$22,$22,$22
B93A 3E 3E 3E	
B93D 2A 7F 7F	
B940 22 22 22	
B943 22 22   	
B945         	DKGRF2
B945 18 18 3C		.BYTE	$18,$18,$3C,$3C,$3C,$3C,$7E,$24,$24,$24,$24
B948 3C 3C 3C	
B94B 7E 24 24	
B94E 24 24   	
B950         	DKGRF3
B950 10 10 38		.BYTE	$10,$10,$38,$38,$38,$7C,$28,$28,$28
B953 38 38 7C	
B956 28 28 28	
B959         	DKGRF4
B959 18 18 3C		.BYTE	$18,$18,$3C,$18,$18
B95C 18 18   	
B95E         	DKGRF5
B95E 10      		.BYTE	$10
B95F         	GBASM6
B95F 10 38 10		.BYTE	$10,$38,$10
             	;
﻿             	;
             	;
B962         	GBASEM
B962 18 7E FF		.BYTE	$18,$7E,$FF,$FF,$FF,$FF,$FF,$E7,$E7,$FF,$FF,$FF,$FF,$FF,$7E,$7E
B965 FF FF FF	
B968 FF E7 E7	
B96B FF FF FF	
B96E FF FF 7E	
B971 7E      	
B972         	GBASM1
B972 00      		.BYTE	0
B973 18 3C 7E		.BYTE	$18,$3C,$7E,$FF,$FF,$FF,$E7,$66,$FF,$FF,$FF,$FF,$7E,$7E
B976 FF FF FF	
B979 E7 66 FF	
B97C FF FF FF	
B97F 7E 7E   	
B981         	GBASM2
B981 00      		.BYTE	0
B982 18 3C 7E		.BYTE	$18,$3C,$7E,$FF,$FF,$E7,$66,$FF,$FF,$FF,$FF,$3C
B985 FF FF E7	
B988 66 FF FF	
B98B FF FF 3C	
B98E         	GBASM3
B98E 18 3C FF		.BYTE	$18,$3C,$FF,$FF,$E7,$66,$FF,$FF,$7E,$3C
B991 FF E7 66
B994 FF FF 7E
B997 3C      
B998         	GBASM4
B998 00      		.BYTE	0
B999 18 3C FF		.BYTE	$18,$3C,$FF,$FF,$FF,$3C,$18
B99C FF FF 3C	
B99F 18      	
B9A0         	GBASM5
B9A0 18 3C FF		.BYTE	$18,$3C,$FF,$3C,$18
             	;
B9A5         	HWARTG		; HWARP TARGET GRAPHIC
B9A5 28 28 28		.BYTE	$28,$28,$28,$28,$EE,0,0,$EE,$28,$28,$28,$28
B9A8 28 EE 00	
B9AB 00 EE 28	
B9AE 28 28 28	
             	;
             	;
             	;
             	;
B9B1         	ZYGRAF		; GRAFIC OF ZYLON SHIP BASED ON XPOS
B9B1 00      		.BYTE	0		; BLANK
B9B2 81 81 81		.BYTE	$81,$81,$81,$81,$BD,$FF,$FF,$BD,$81,$81,$81,$81
B9B5 81 BD FF	
B9B8 FF BD 81	
B9BB 81 81 81	
B9BE         	ZYGRF1
B9BE 82 82 BA		.BYTE	$82,$82,$BA,$FE,$FE,$BA,$82,$82
B9C1 FE FE BA	
B9C4 82 82   	
B9C6         	ZYGRF2
B9C6 42 5A 7E		.BYTE	$42,$5A,$7E,$7E,$5A,$42
B9C9 7E 5A 42
B9CC         	ZYGRF3
B9CC 44 54 7C		.BYTE	$44,$54,$7C,$7C,$54,$44
B9CF 7C 54 44	
B9D2         	ZYGRF4
B9D2 24 3C 3C		.BYTE	$28,$38,$38,$28
B9D9 24      	
B9DA         	ZYGRF6
B9DA 18 18   		.BYTE	$18,$18
             	;
             	;
B9DC         	ZYGRF7
B9DC 10 10   		.BYTE	$10,$10
B9DE         	GBASER
B9DE E0 F8 F8		.BYTE	$E0,$F8,$F8,$FE,$57,$FE,$F8,$F8,$C0
B9E1 FE 57 FE	
B9E4 F8 F8 C0	
B9E7         	GBASR3
B9E7 C0 F0   		.BYTE	$C0,$F0
B9E9         	GBASR1
B9E9 C0 F0 F0		.BYTE	$C0,$F0,$F0,$FC,$BE,$FC,$F0,$80,$80
B9EC FC BE FC	
B9EF F0 80 80	
B9F2         	GBASR2
B9F2 C0 C0 F0		.BYTE	$C0,$C0,$F0,$BC,$F0,$C0
B9F5 BC F0 C0	
             	;
             	;
             	;
B9F8         	GBASEL
B9F8 07 1F 1F		.BYTE	7,$1F,$1F,$7F,$EA,$7F,$1F,$1F,$3
B9FB 7F EA 7F	
B9FE 1F 1F 03	
BA01         	GBASL3
BA01 03 0F   		.BYTE	3,$F
BA03         	GBASL1
BA03 03 0F 0F		.BYTE	3,$F,$F,$3F,$7D,$3F,$F,1,1
BA06 3F 7D 3F	
BA09 0F 01 01	
BA0C         	GBASL2
BA0C 03 03 0F		.BYTE	3,3,$F,$3D,$F,3
BA0F 3D 0F 03	
             	;
             	;
             	;
             	;
BA12         	ROGRAF
BA12 18 3C 7E		.BYTE	$18,$3C,$7E,$7E,$DB,$C3,$81,$81,$81
BA15 7E DB C3	
BA18 81 81 81	
BA1B         	ROGRF1
BA1B 10 38 7C		.BYTE	$10,$38,$7C,$7C,$D6,$C6,$82,$82
BA1E 7C D6 C6	
BA21 82 82   	
BA23         	ROGRF2
BA23 18 3C 3C		.BYTE	$18,$3C,$3C,$66,$66,$42,$42
BA26 66 66 42	
BA29 42      	
BA2A         	ROGRF3
BA2A 10 38 38		.BYTE	$10,$38,$38,$6C,$44,$44
BA2D 6C 44 44	
BA30         	ROGRF4
BA30 18 3C 24		.BYTE	$18,$3C,$24,$24
BA33 24      	
             	;
             	;
BA34         	ROGRF5
BA34 10 38 28		.BYTE	$10,$38,$28
             	;
             	;
BA37         	KLGRAF
BA37 18 3C 7E		.BYTE	$18,$3C,$7E,$FF,$18,$18,$FF,$7E,$3C,$18
BA3A FF 18 18	
BA3D FF 7E 3C	
BA40 18      	
BA41         	KLGRF1
BA41 10 38 7C		.BYTE	$10,$38,$7C,$FE,$38,$38,$FE,$7C,$38,$10
BA44 FE 38 38	
BA47 FE 7C 38	
BA4A 10      	
BA4B         	KLGRF2
BA4B 18 3C 7E		.BYTE	$18,$3C,$7E,$18,$7E,$3C,$18
BA4E 18 7E 3C	
BA51 18      	
BA52         	KLGRF3
BA52 10 38 7C		.BYTE	$18,$3C,$18,$3C,$18
BA55 10 7C 38	
BA5C 3C 18   	
BA5E         	KLGRF5
BA5E 10 38 38		.BYTE	$10,$38,$38,$10
BA61 10      	
             	;
             	;
             	;
             	;
BA62         	LISTAB		; DISPLAY LIST TABLE  LDISP
             	;	SHIP ALIVE
BA62 82 00 46		.BYTE	$8D,0,$46
BA65 49 09   		.WORD	DISCTL
BA67 20 06 00		.BYTE	$20,6,0
BA6A         	LISTB2		; GAL CHT
BA6A 01      		.BYTE	1
BA6B 2E A1   		.WORD	GLDISP
BA6D         	LISTB3		; SECT SCAN
BA6D 00 00 46		.BYTE	0,0,$46
BA70 F8 A0   		.WORD	SESCAN
BA72 4D      		.BYTE	$4D
BA73 C8 10   		.WORD	MEMMAP+200
BA75         	LISTB4		; BACK VIEW
BA75 00 00 46		.BYTE	0,0,$46
BA78 09 A1   		.WORD	BACKUP
BA7A 4D      		.BYTE	$4D
BA7B C8 10   		.WORD	MEMMAP+200
BA7D         	LISTB5		; FRONT VIEW
BA7D 4D      		.BYTE	$4D
BA7E 00 10   		.WORD	MEMMAP
BA80 0D 0D 0D		.BYTE	$0D,$0D,$0D,$0D,$0D
BA83 0D 0D   	
BA85         	LISTB6		; MESSAGE ON
BA85 30 46   		.BYTE	$30,$46
BA87 1F 0D   		.WORD	MESAGE
BA89 4D      		.BYTE	$4D
BA8A A8 12   		.WORD	MEMMAP+680
             	;
             	;
BA8C         	DISDIS		; FOR KEYSRV  , DISPLAY LIST POINTERS
BA8C 1B 13 0B		.BYTE	LISTB5-LISTAB,LISTB4-LISTAB,LISTB3-LISTAB,LISTB2-LISTAB
BA8F 08      	
             	;
             	;
BA90         	BRTABL		; BRIGHTNESS SELECT TABLE
BA90 FF FF FF		.BYTE	BRT,BRT,BRT,BRT
BA93 FF      	
BA94 AA FF AA		.BYTE	MED,BRT,MED,BRT
BA97 FF      	
BA98 AA AA AA		.BYTE	MED,MED,MED,BRT
BA9B FF      	
BA9C AA AA AA		.BYTE	MED,MED,MED,MED
BA9F AA      	
BAA0 AA AA AA		.BYTE	MED,MED,MED,DIM
BAA3 55      	
BAA4 55 AA 55		.BYTE	DIM,MED,DIM,MED
BAA7 AA      	
BAA8 55 55 55		.BYTE	DIM,DIM,DIM,MED
BAAB AA      	
BAAC 55 55 55		.BYTE	DIM,DIM,DIM,DIM
BAAF 55      	
             	;
             	;
BAB0         	MASK		; MASK FOR RAM MAP BYTE DUE TO HPOS
BAB0 C0 30 0C		.BYTE	$C0,$30,$0C,$03
BAB3 03      	
             	;
             	;
BAB4         	WARPTB		; SELECT WARP ACCEL FROM KEY 0-9
BAB4 00 01 02		.BYTE	0,$01,$02,$04,$08,$10,$20,$40,$60,$70
BAB7 04 08 10	
BABA 20 40 60	
BABD 70      	
             	;
             	;
BABE         	CODCON		; USED IN KEYSRV SUBROUTINE FOR KEY CONVERT
BABE F2 DF DE		.BYTE	$F2,$DF,$DE,$DA,$D8,$DD,$DB,$F3,$F5,$F0
BAC1 DA DB DD	
BAC4 DB F3 F5	
BAC7 F0      	
BAC8 F8 FF C0		.BYTE	$F8,$FF,$C0,$FD,$EF,$FE,$D2,$F9,$E5,$CA
BACB FD ED FE	
BACE D2 F9 E5	
BAD1 CA      	
BAD2 E7      		.BYTE	$E7
             	;
BAD3         	WENTAB			; ENERGY USED PER WARP
BAD3 00 04 06		.BYTE	0,4,6,8,10,12,14,30,45,60
BAD6 08 0A 0C	
BAD9 0E 1E 2D	
BADC 3C      	
             	;
             	;
             	;
             	;
             	;
             	;
             	;
             	;
BADD         	ENGTAB			; ENERGY USED PER DISTANCE WARP JUMP
BADD 0A 0D 10		.BYTE	10,13,16,20,23,50,70,80,90,120,125,130,135,140,155,170,184,200
BAE0 14 17 32	
BAE3 46 50 5A	
BAE6 78 7D 82	
BAE9 87 8C 9B	
BAEC AA B8 C8	
BAEF D0 D8 DF		.BYTE	208,216,223,232,241,250
BAF2 E8 F1 FA	
             	;
             	;
             	;
             	;
             	;
BAF5         	JOYTAB		; CODE FOR EACH POSITION ON JOYSTICK
BAF5 00 01 FF		.BYTE	0,$1,$FF,0
BAF8 00      	
             	;
             	;
             	;
BAF9         	INSTAB		; INSET LINES TABLE    HDRAW,VDRAW,NUMPTS
BAF9 50 28 87		.BYTE	$50,$28,$87,$50,$36,$87
BAFC 50 36 87	
BAFF 77 46 1E		.BYTE	119,70,30,119,86,30,119,70,$91,148,70,$91
BB02 77 56 1E	
BB05 77 46 91	
BB08 94 46 91	
BB0B 78 4E 06		.BYTE	120,78,6,126,75,15,126,81,15,141,78,7
BB0E 7E 4B 0F	
BB11 7E 51 0F	
BB14 8D 4E 07	
BB17 85 47 84		.BYTE	133,71,$84,126,76,$85,140,76,$85,133,82,$84
BB1A 7E 4C 85	
BB1D 8C 4C 85	
BB20 85 52 84	
             	;
             	;
BB23         	INSTB1		; HORIZ CROSS HAIRS
BB23 3E 32 0F		.BYTE	$3E,$32,15,$54,$32,15
BB26 54 32 0F	
BB29 FE      		.BYTE	$FE			; ALL DONE
             	;
BB2A         	INSTB2			; SECTOR SCAN SHIP
BB2A 4E 35 82		.BYTE	$4E,$35,$82,$4F,$34,$82,$50,$32,$85,$51,$34,$82,$52,$35,$82
BB2D 4F 34 82	
BB30 50 32 85	
BB33 51 34 82	
BB36 52 35 82	
BB39 FF      		.BYTE	$FF			; ALL DONE
             	;
             	;
             	;
             	;
             	;
             	;
             	;
BB3A         	YINIT		; HLINES
BB3A 04 04 03		.BYTE	4,4,3,2
BB3E 02      	
BB3E         	ZINIT		; HLINES
BB3E 02 03 04		.BYTE	2,3,4,4
BB41 04      	
             	;
             	;
             	;
             	;
             	;
             	;
             	;
             	;
             	;
             	;
BB42         	STINT		; STATUS INIT TABLE (LDTABS)
BB42 12 0B 00		.BYTE	18,11,0,0,10,$55,$4B,$40,$40,10,$8D,$8B,$89,$89,$89,$89
BB45 00 0A 55	
BB48 4B 40 40	
BB4B 0A 8D 8B	
BB4E 89 89 89	
BB51 89      	
BB52 0A 16 0B		.BYTE	10,$16,11,0
BB55 00      	
BB56 0A      		.BYTE	10
BB57 14 0B 0F		.BYTE	$14,$0B,$04,0,0,10,$51,$4B,$0F,0,0,10,$93,$8B,$0F,0,0,0
BB5A 00 00 0A	
BB5D 51 4B 0F	
BB60 00 00 0A	
BB63 93 8B 0F	
BB66 00 00 00	
BB69 0A      		.BYTE	10
BB6A 37 21 32		.BYTE	$37,$21,$32,$30,0,$25,$2E,$25,$32,$27,$39,$1A,0,0,0
BB6D 30 00 25	
BB70 2E 25 32	
BB73 27 39 1A	
BB76 00 00 00	
BB79 10 00 00		.BYTE	$10,0,0,0,0
BB7C 00 00   	
BB7E B4 A1 B2		.BYTE	$B4,$A1,$B2,$A7,$A5,$B4,$B3,$9A,0,0
BB81 A7 A5 B4	
BB84 B3 9A 00	
BB87 00      	
BB88 24 23 1A		.BYTE	$24,$23,$1A,$30,$25,$33,$23,$2C,$32
BB8B 30 25 33	
BB8E 23 2C 32	
BB91 00      		.BYTE	0
BB92 F3 F4 E1		.BYTE	$F3,$F4,$E1,$F2,0,$E4,$F4,$E5,$DA,$D0,$D0,$CE,$D0
BB95 F2 00 E4	
BB98 E1 F4 E5	
BB9B DA D0 D0	
BB9E CE D0   	
BBA0 D0 00 00		.BYTE	$D0,0,0,0,0,0
BBA3 00 00 00	
             	;
BBA6         	CHRTAB		; TABLE FOR LDTABS ROUTINE
BBA6 CF 04 03		.BYTE	$CF,4,3,2
BBA9 02      	
             	;
             	;
             	;
             	;
             	;
             	;
BBAA         	SENTAB		; TABLE OF SENTENSES
BBAA 00      		.BYTE	0		; BUFFER
BBAB         	SENACN				; ATTACK COMPUTER ON
BBAB 05 06 42		.BYTE	5,6,$42
BBAE         	SENACF				; ATTACK COMPUTER OFF
BBAE 05 06 43		.BYTE	5,6,$43
BBB1         	SENSON				; SHIELDS ON
BBB1 04 42   		.BYTE	4,$42
BBB3         	SENSOF				; SHIELDS OFF
BBB3 04 43   		.BYTE	4,$43
BBB5         	SENCTN				; COMPUTER TRACKING ON
BBB5 06 07 42		.BYTE	6,7,$42
BBB8         	SENCTF				; COMPUTER TRACKING OFF
BBB8 07 43   		.BYTE	7,$43
BBBA         	SENWHT				; WHAT?
BBBA 48      		.BYTE	$48
BBBB         	SENHYP				; HYPERWARP ENGAGED
BBBB 09 4A   		.BYTE	9,$4A
BBBD         	SENSUR
BBBD 0B CD   		.BYTE	11,$CD		; STARBASE SURROUNDED
BBBF         	SENDES
BBBF 0B CC   		.BYTE	11,$CC		; STARBASE DESTROYED
BBC1         	SENHWA			; HYPERWARP ABORTE
BBC1 09 4E   		.BYTE	9,$4E
BBC3         	SENHWC				; HYPERWARD COMPLETE
BBC3 09 4F   		.BYTE	9,$4F
BBC5         	SENHSP				; HYPERSPACE
BBC5 D0      		.BYTE	$D0
BBC6         	SENORB		; ORBIT ESTABLISHED
BBC6 11 92 56		.BYTE	17,$92,$56
BBC9         	SENDKA		; DOCKING ABORTED
BBC9 13 4E   		.BYTE	19,$4E
BBCB         	SENETC			; ENERGY TRANSFER COMPLETE
BBCB 15 4F   		.BYTE	21,$4F
BBCD         	SENDST		; YOU ARE DESTROYED
BBCD B8 97 99		.BYTE	$B8,$97,$99,$98,$8C,$9D,30,$9F,$FD,37,$FC,$78
BBD0 98 8C 9D	
BBD3 1E 9F FD	
BBD6 25 FC 78	
BBD9         	SENATA		; TITLE
BBD9 9B 60   		.BYTE	$9B,$60
             	;
             	;
BBDB         	SENOUT		; OUT OF ENERGY
BBDB B8 97 98		.BYTE	$B8,$97,$98,26,$8E,28,$94,36,$9F,$FD,37,$FC,$A7,$68
BBDE 1A 8E 1C	
BBE1 94 24 9F	
BBE4 FD 25 FC	
BBE7 A7 68   	
BBE9         	SENWIN		; YOU WIN
BBE9 B8 97 98		.BYTE	$B8,$97,$98,26,$8F,36,$9F,$FD,37,$FC,$66
BBEC 1A 8F 24	
BBEF 9F FD 25	
BBF2 FC 66   	
BBF4         	SENNOV		; NOVICE MISSION
BBF4 2C 5A   		.BYTE	44,$5A
BBF6         	SENPIL		; PILOT MISSION
BBF6 2E 5A   		.BYTE	46,$5A
BBF8         	SENWAR		; WARRIOR MISSION
BBF8 31 5A   		.BYTE	49,$5A
             	;
             	;
BBFA         	SENCOM			; COMMANDER MISSION
BBFA 33 5A   		.BYTE	51,$5A
BBFC         	SENDMC	; DAMAGE CONTROL
BBFC B8 34 76		.BYTE	$B8,52,$76
BBFF         	SENPDM		; PHOTONS DAMAGED
BBFF 37 B5 78		.BYTE	55,$B5,$78
BC02         	SENPDS		; PHOTONS DESTROYED
BC02 37 8C 78		.BYTE	55,$8C,$78
BC05         	SENEDM		; ENGINES DAMAGED
BC05 23 B5 78		.BYTE	35,$B5,$78
BC0B         	SENSDM		; SHIELDS DAMAGED
BC0B 04 B5 78		.BYTE	4,$B5,$78
BC0E         	SENSDS		; SHIELDS DESTROYED
BC0E 04 8C 78		.BYTE	4,$8C,$78
BC11         	SENCDM	; COMPUTER DAMAGED
BC11 06 B5 78		.BYTE	6,$B5,$78
BC14         	SENCDS		; COMPUTER DESTROYED
BC14 06 8C 78		.BYTE	6,$8C,$78
BC17         	SENTDM		; SECTOR SCAN DAMAGED
BC17 A2 75   		.BYTE	$A2,$75
BC19         	SENTDS		; SECTOR SCAN DESTROYED
BC19 A2 4C   		.BYTE	$A2,$4C
BC1B         	SENMDM		; COMMUNICATIONS DAMAGED
BC1B A1 75   		.BYTE	$A1,$75
BC1D         	SENMDS		; COMMUNICATIONS DESTROYED
BC1D A1 4C   		.BYTE	$A1,$4C
BC1F         	SENRED		; RED ALERT
BC1F C1      		.BYTE	$C1
BC20         	SENABR		; MISSION ABORTED KEY
BC20 B8 97 98		.BYTE	$B8,$97,$98,26,$8E,36,$9F,$FD,37,$FC,$66
BC23 1A 8E 24	
BC26 9F FD 25	
BC29 FC 66   	
             	;
             	;
             	;
BC2B         	WRDTAB			; TABLE OF WORDS
BC2B A0 20 20		.BYTE	$A0,"    RED ALERT"
BC2E 20 20 52	
BC31 45 44 20	
BC34 41 4C 45	
BC37 52 54   	
BC39 CF 4E   		.BYTE	$CF,"N"
BC3B CF 46 46		.BYTE	$CF,"FF"
BC3E D3 48 49		.BYTE	$D3,"HIELDS"
BC41 45 4C 44	
BC44 53      	
BC45 C1 54 54		.BYTE	$C1,"TTACK"
BC48 41 43 4B	
BC4B C3 4F 4D		.BYTE	$C3,"OMPUTER"
BC4E 50 55 54	
BC51 45 52   	
BC53 D4 52 41		.BYTE	$D4,"RACKING"
BC56 43 4B 49	
BC59 4E 47   	
BC5B D7 48 41		.BYTE	$D7,"HATS WRONG?"
BC5E 54 53 20	
BC61 57 52 4F	
BC64 4E 47 3F	
BC67 C8 59 50		.BYTE	$C8,"YPERWARP"
BC6A 45 52 57	
BC6D 41 52 50	
BC70 C5 4E 47		.BYTE	$C5,"NGAGED"
BC73 41 47 45	
BC76 44      	
             	;
             	;
BC77 D3 54 41		.BYTE	$D3,"TARBASE"
BC7A 52 42 41	
BC7D 53 45   	
BC7F C4 45 53		.BYTE	$C4,"ESTROYED"
BC82 54 52 4F	
BC85 59 45 44	
BC88 D3 55 52		.BYTE	$D3,"URROUNDED"
BC8B 52 4F 55	
BC8E 4E 44 45	
BC91 44      	
BC92 C1 42 4F		.BYTE	$C1,"BORTED"
BC95 52 54 45	
BC98 44     	
BC99 C3 4F 4D		.BYTE	$C3,"COMPLETE"
BC9C 50 4C 45	
BC9F 54 45   	
BCA1 C8 59 50		.BYTE	$C8,"YPERSPACE"
BCA4 45 52 53	
BCA7 50 41 43	
BCAA 45      	
BCAB CF 52 42		.BYTE	$CF,"RBIT"
BCAE 49 54   	
BCB0 C5 53 54		.BYTE	$C5,"STABLISHED"
BCB3 41 42 4C	
BCB6 49 53 48	
BCB9 45 44   	
BCBB C4 4F 43		.BYTE	$C4,"OCKING"
BCBE 4B 49 4E	
BCC1 47      	
BCC2 C5 4E 45		.BYTE	$C5,"NERGY"
BCC5 52 47 59	
BCC8 D4 52 41		.BYTE	$D4,"RANSFER"
BCCB 4E 53 46	
BCCE 45 52   	
BCD0 D3 54 41		.BYTE	$D3,"TANDBY"
BCD3 4E 44 42	
BCD6 59      	
BCD7 D3 54 41		.BYTE	$D3,"TAR FLEET TO"
BCDA 52 20 46	
BCDD 4C 45 45	
BCE0 54 20 54	
BCE3 4F      	
BCE4 D3 54 41		.BYTE	$D3,"TAR CRUISER 7"
BCE7 52 20 43	
BCEA 52 55 49	
BCED 53 45 52	
BCF0 20 37   	
             	;
             	;
BCF2 C1 4C 4C		.BYTE	$C1,"LL UNITS"
BCF5 20 55 4E	
BCF8 49 54 53	
BCFB CD 49 53		.BYTE	$CD,"ISSION"
BCFE 53 49 4F	
BD01 4E      	
BD02 A0 20 20		.BYTE	$A0,"  STAR RAIDERS"
BD05 20 53 54	
BD08 41 52 20	
BD0E 44 45 52	
BD11 53      	
BD12 DA 45 52		.BYTE	$DA,"ERO"
BD15 4F      	
BD16 C2 59 20		.BYTE	$C2,"Y ZYLON FIRE"
BD19 5A 59 4C	
BD1C 4F 4E 20	
BD1F 46 49 52	
BD22 45      	
BD23 D0 4F 53		.BYTE	$D0,"OSTHUMOUS"
BD26 54 48 55	
BD29 4D 4F 55	
BD2C 53      	
BD2D D2 41 4E		.BYTE	$D2,"AND IS:"
BD30 4B 20 49	
BD33 53 3A   	
BD35 C3 4F 50		.BYTE	$C3,"OPYRIGHT ATARI 1979"
BD38 59 52 49	
BD38 59 52 49	
BD3E 47 48 54	
BD3E 20 41 54	
BD41 41 52 49	
BD44 20 31 39	
BD47 37 39   	
BD49 D3 55 42		.BYTE	$D3,"UB-SPACE RADIO"
BD4C 2D 53 50	
BD4F 41 43 45	
BD52 44 49 4F	
BD58 D3 45 43		.BYTE	$D3,"ECTOR SCAN"
BD5B 54 4F 52	
BD5E 20 53 43	
BD61 41 4E   	
BD63 C5 4E 47		.BYTE	$C5,"NGINES"
BD66 79 4E 45	
BD69 53      	
BD6A CE 45 57		.BYTE	$CE,"EW"
BD6D C3 4C 41		.BYTE	$C3,"LASS"
BD70 53 53   	
BD72 C3 4F 4E		.BYTE	$C3"ONGRATULATIONS"
BD75 47 52 41	
BD78 54 55 4C	
BD7B 41 54 49	
BD7E 4F 4E 53	
             	;
             	;
BDB1 D2 45 50		.BYTE	$D2,"EPORT TO BASE"
BDB4 4F 52 54	
BDB7 20 54 4F	
BDBA 20 42 41	
BDBD 53 45   	
BD8F C6 4F 52		.BYTE	$C6,"OR TRAINING"
BD92 20 54 52	
BD95 41 49 4E	
BD98 49 4E 47	
BD9B C7 41 4C		.BYTE	$C7,"ALACTIC COOK"
BD9E 41 43 54	
BDA1 49 43 20	
BDA4 43 4F 4F	
BDA7 4B      	
BDA8 C7 41 52		.BYTE	$C7,"ARBAGE SCOW CAPTAIN"
BDAB 42 41 47	
BDAE 45 20 53	
BDB1 43 4F 57	
BDBA 49 4E   	
BDBC D2 4F 4F		.BYTE	$D2,"OOKIE"
BDBF 4B 49 45	
BDC2 CE 4F 56		.BYTE	$CE,"OVICE"
BDC5 49 43 45	
BDC8 C5 4E 53		.BYTE	$C5,"NSIGN"
BDCB 49 47 4E	
BDCE D0 49 4C		.BYTE	$D0,"ILOT"
BDD1 4F 54   	
BDD3 C1 43 45		.BYTE	$C1,"CE"
BDD6 CC 49 45		.BYTE	$CC,"IEUTENANT"
BDD9 55 54 45	
BDDC 4E 41 4E	
BDDF 54      	
BDE0 D7 41 52		.BYTE	$D7,"ARRIOR"
BDE3 52 49 4F	
BDE6 52      	
BDE7 C3 41 50		.BYTE	$C3,"APTAIN"
BDEA 54 41 49	
BDED 4E      	
             	;
             	;
BDEE C3 4F 4D		.BYTE	$C3,"OMMANDER"
BDF1 4D 41 4E	
BDF4 44 45 52	
BDF7 C4 41 4D		.BYTE	$C4,"AMAGE"
BDFA 41 47 45	
BDFD C4 41 4D		.BYTE	$C4,"AMAGED"
BE00 41 47 45	
BE03 44      	
BE04 C3 4F 4E		.BYTE	$C3,"ONTROL"
BE07 54 52 4F	
BE0A 4C      	
BE0B D0 48 4F		.BYTE	$D0,"HOTONS"
BE0E 54 4F 4E	
BE11 53      	
             	;
BE12 A0      		.BYTE	$A0		; BLANK
BE13 D3 54 41		.BYTE	$D3,"TAR COMMANDER"
BE16 52 20 43	
BE19 4F 4D 4D	
BE1C 41 4E 44	
BE1E 45 52   	
BE21 80      		.BYTE	$80		; END TABLE
             	;
             	;
             	;
             	;
BE22         	DISTYP			; CODE TO LOAD IN DISFLG
BE22 00 01 40		.BYTE 0,1,$40,$80
BE25 80      	
BE26         	TOFFMG		; POINTER TO TOGLE OFF MESSAGE
BE26 0E 09 04		.BYTE	SENCTF-SENTAB,SENSOF-SENTAB,SENACF-SENTAB
BE29         	TOGTAB			; BYTE TO TOGGLE RAM BYTE WITH
BE29 FF 08 02		.BYTE	$FF,8,2
BE2C        	TONMSG		; POINTER TO TOGGLE ON MESSAGE
BE2C 0B 07 01		.BYTE	SENCTN-SENTAB,SENSON-SENTAB,SENACN-SENTAB
             	;
             	;
             	;
             	;
             	;
BE2F         	GPOINT		; TABLE OF GRAPHIC POINTERS FOR THE OBJ (OBJCOL)
BE2F 01 11 1F		.BYTE	1,PHGRF1-PHGRAF,PHGRF2-PHGRAF,PHGRF3-PHGRAF,PHGRF4-PHGRAF
BE32 2B 35   	
BE34 3D 75 7A		.BYTE	PHGRF5-PHGRAF,DKGRF4-PHGRAF,DKGRF5-PHGRAF
BE37 01 0D 15		.BYTE	1,ZYGRF1-ZYGRAF,ZYGRF2-ZYGRAF,ZYGRF3-ZYGRAF,ZYGRF4-ZYGRAF
BE3A 1B 21   	
BE3C 25 29 2B		.BYTE	ZYGRF5-ZYGRAF,ZYGRF6-ZYGRAF,ZYGRF7-ZYGRAF
BE3F 2D      		.BYTE	GBASER-ZYGRAF
BE40 38 41 36		.BYTE	GBASR1-ZYGRAF,GBASR2-ZYGRAF,GBASR3-ZYGRAF,GBASR3-ZYGRAF,0,0,0
BE43 36 00 00	
BE46 00      	
BE47 7E      		.BYTE	GBASEM-PHGRAF
BE48 8E 9D AA		.BYTE	GBASM1-PHGRAF,GBASM2-PHGRAF,GBASM3-PHGRAF,GBASM4-PHGRAF
BE4B B4      	
BE4C BC 7B 7A		.BYTE	GBASM5-PHGRAF,GBASM6-PHGRAF,DKGRF5-PHGRAF
BE4F 47      		.BYTE	GBASEL-ZYGRAF
BE50 52 5B 50		.BYTE	GBASL1-ZYGRAF,GBASL2-ZYGRAF,GBASL3-ZYGRAF,GBASL3-ZYGRAF,0,0,0
BE53 50 00 00	
BE56 00      	
BE57 43      		.BYTE	DKGRAF-PHGRAF
BE58 53 61 6C		.BYTE	DKGRF1-PHGRAF,DKGRF2-PHGRAF,DKGRF3-PHGRAF,DKGRF4-PHGRAF
BE5B 75      	
BE5C 7A 75 7A		.BYTE	DKGRF5-PHGRAF,DKGRF4-PHGRAF,DKGRF5-PHGRAF
BE5F 01 11 1F		.BYTE	1,PHGRF1-PHGRAF,PHGRF2-PHGRAF,PHGRF3-PHGRAF,PHGRF4-PHGRAF
BE62 2B 35   	
BE64 3D 75 7A		.BYTE	PHGRF5-PHGRAF,DKGRF4-PHGRAF,DKGRF5-PHGRAF
             	;
             	;
             	;
             	;
BE67 61      		.BYTE	ROGRAF-ZYGRAF
BE68 6A 72 79		.BYTE	ROGRF1-ZYGRAF,ROGRF2-ZYGRAF,ROGRF3-ZYGRAF,ROGRF4-ZYGRAF
BE6B 7F      	
BE6C 83 29 2B		.BYTE	ROGRF5-ZYGRAF,ZYGRF6-ZYGRAF,ZYGRF7-ZYGRAF
BE6F 86      		.BYTE	KLGRAF-ZYGRAF
BE70 90 9A A1		.BYTE	KLGRF1-ZYGRAF,KLGRF2-ZYGRAF,KLGRF3-ZYGRAF,KLGRF4-ZYGRAF
BE73 A8      	
BE74 AD 29 2B		.BYTE	KLGRF5-ZYGRAF,ZYGRF6-ZYGRAF,ZYGRF7-ZYGRAF
BE77 C1 C1 C1		.BYTE	HWARTG-PHGRAF,HWARTG-PHGRAF,HWARTG-PHGRAF,HWARTG-PHGRAF
BE7A C1      	
BE7B C1 C1 75		.BYTE	HWARTG-PHGRAF,HWARTG-PHGRAF,DKGRF4-PHGRAF,HWARTG-PHGRAF
BE7C C1      	
             	;
BE7F         	NBYTAB		; NUMBER OF BYTES TO STORE  ( OBJCOL)
BE7F 0F 0D 0B		.BYTE	15,13,11,9,7,5,1,1
BE82 09 07 05	
BE85 01 01   	
BE87 0B 07 05		.BYTE	11,7,5,5,3,3,1,1
BE8A 05 03 03	
BE8D 01 01   	
BE8F 09 08 05		.BYTE	9,8,5,2,0,0,0,0
BE92 02 00 00	
BE95 00 00   	
BE97 0F 0E 0C		.BYTE	15,14,12,9,7,4,2,1
BE9A 09 07 04	
BE9D 02 01   	
BE9F 09 08 05		.BYTE	9,8,5,2,0,0,0,0
BEA2 02 00 00	
BEA5 00 00   	
BEA7 0F 0D 0B		.BYTE	15,13,10,8,4,3,1,1
BEAA 08 04 03	
BEAD 01 01   	
BEAF 0F 0D 0B		.BYTE	15,13,11,9,7,5,1,1
BEB2 09 07 05	
BEB5 01 01   	
BEB7 08 07 06		.BYTE	8,7,6,5,3,2,1,1
BEBA 05 03 02	
BEBD 01 01   	
BEBF 09 09 06		.BYTE	9,9,6,6,4,3,1,1
BEC2 06 04 03	
BEC5 01 01   	
BEC7 0B 0B 0B		.BYTE	11,11,11,11,11,11,1,11
BECA 0B 0B 0B	
BECD 01 0B   	
             	;
             	;
             	;
             	;
             	;
BECF         	TRKTAB		; KEY FOR SWITCHING DISPLAY, ASERVE
BECF F8 FF   		.BYTE	$F8,$FF
BED1         	CHTABL	; FOR LDGALT, CODES FOR CHTDIS
BED1 0C 1E 1E		.BYTE	$0C,$1E,$1E,$1D,$1C,$1B
BED4 1D 1C 1B	
             	;
             	;
             	;
BED7         	STERTB		; USED IN HWARP STEERING , OBJCOL
BED7 9F BF DF		.BYTE	$9F,$BF,$DF,$FF
BEDA FF      	
             	;
             	;
             	;
BEDB         	BHORTB		; STAR BASE HORIZ OFFSET TABLE
BEDB F8 08   		.BYTE	$F8,08
             	;
             	;
BEDD         	DIFTAB		; RATING,$DIFFICULTY TABLE
BEDD 50 4C 3C		.BYTE	80,76,60,111,60,60,50,100,40,50,40,90
BEE0 6F 3C 3C	
BEE3 32 64 28	
BEE6 32 28 5A	
BEE9         	RANKTB		; RAND WORD VS. RATING HI NIBBLE
BEE9 A9 AA AA		.BYTE	$A9,$AA,$AA,$AB,$AB,$AC,$AC,$AD,$AD,$AE,$AE,$AF,$B0,$B1,$B2,$B3
BEEC AB AB AC	
BEEF AC AD AD	
BEF2 AE AE AF	
BEF5 B0 B1 B2	
BEF8 B3      	
BEF9 B3 B9 B9		.BYTE	$B3,$B9,$B9
             	;
             	;
BEFC         	CLASTB		; DMA ASCII CLASS VS RATING LO NIBBLE
BEFC 95 95 95		.BYTE	$95,$95,$95,$94,$94,$94,$94,$93,$93,$93,$92,$92,$92,$91
BEFF 94 94 94	
BF02 94 93 93	
BF05 93 92 92	
BF08 92 91   	
BF0A 91 91   		.BYTE	$91,$91
             	;
BF0C         	MSENTB		; MISSION TYPE TABLE
BF0C 4A 4C 4E		.BYTE	SENNOV-SENTAB,SENPIL-SENTAB,SENWAR-SENTAB,SENCOM-SENTAB
BF0F 50      	
BF10         	DPRBTB		; DAMAGE PROB BASED ON MISDIF
BF10 00 50 B4		.BYTE	0,80,180,$FE
BF13 FE      	
BF14         	DAMGTB		; SENTENCES FO DAMAGE (DAMCTL)
BF14 55 5B 61		.BYTE	SENPDM-SENTAB,SENEDM-SENTAB,SENSDM-SENTAB,SENCDM-SENTAB
BF17 67      	
BF18 6D 71   		.BYTE	SENTDM-SENTAB,SENMDM-SENTAB
BF1A         	DESTTB		; SENTENCES FO DESTROY (DAMCTL)
BF1A 58 5E 64		.BYTE	SENPDS-SENTAB,SENEDS-SENTAB,SENSDS-SENTAB,SENCDS-SENTAB
BF1D 6A      	
BF1E 6F 73   		.BYTE	SENTDS-SENTAB,SENMDS-SENTAB
             	;
             	;
BF20         	NOISTB	; NOISE ROUTINE, INIT AUDTIM,AUDADD,AFREQ2,AFREQ1,ATYPE3
             			; ATYPE2,AUDEXP,PHOREP,AUDCTL,AUDF3
             	;	FOR PHOTONS
BF20 18 FF 02		.BYTE	$18,$FF,2,0,$8A,$A0,0,8,$50,$00
BF23 00 8A A0	
BF26 00 08 50	
BF29 00      	
BF2A         	NOITB1		; FOR SHIELD EXPLOSION
BF2A 40 40 01		.BYTE	$40,$40,1,3,$88,$AF,8,0,$50,4
BF2D 03 88 AF	
BF30 08 00 50	
BF33 04      	
BF34         	NOITB2		; FOR ZYLON EXPLOS
BF34 30 40 01		.BYTE	$30,$40,1,3,$84,$A8,4,0,$50,4
BF37 03 84 A8	
BF3A 04 00 50	
BF3D 04      	
             	;
             	;
             	;
BF3E         	CH4TAB		; NOTINT,	INIT REPPTR,NPRIOR,SDURAT,NDURAT,REPSEQ,NOTSEQ
BF3E         	CH4TB1		; HYPERSPACE
BF3E 02 02 02		.BYTE	2,2,2,3,12,2
BF41 03 0C 02	
BF44         	CH4TB2		; RED ALERT
BF44 04 03 FF		.BYTE	4,3,$FF,$10,7,4
BF47 10 07 04	
BF4A         	CH4TB3		; KEYS
BF4A 07 04 02		.BYTE	7,4,2,2,0,7
BF4D 02 00 07	
BF50         	CH4TB4		; DAMAGE
BF50 0B 05 FF		.BYTE	11,5,$FF,$20,2,11
BF53 20 02 0B	
BF56         	CH4TB5		; MESSAGE
BF56 0E 06 08		.BYTE	14,6,8,$20,0,14
BF59 20 00 0E	
             	;
             	;
             	;
BF5C         	NOTTAB		; TABL O NOTES, FF=RESERVED BYTE
BF5C 10 FF   		.BYTE	$10,$FF			; TRACKING
BF5E 18 FF   		.BYTE	$18,$FF			; HYPERSPACE
BF60 40 60 FF		.BYTE	$40,$60,$FF		; RED ALERT
BF63 10 10 10		.BYTE	$10,$10,$10,$FF		; KEYS
BF66 FF      	
BF67 40 20 FF		.BYTE	$40,$20,$FF		; DAMAGE
BF6A 48 40 51		.BYTE	$48,$40,$51,$FF		; STARFLEET MESSAGE
BF6D FF      	
             	;
             	;
BF6E         	ZYTARG			; GRAPHIC OF ZYLON TARGET
BF6E 84 B4 FC		.BYTE	$84,$B4,$FC,$B4,$84
BF71 B4 84   	
             	;
             	;
             	;
             	;
BF73         	PHOYPS		; YPOSH FOR PHOTON
BF73 FF 01   		.BYTE	$FF,1
             	;
BF75         	PHPOST		; BOUNDS IN HITZYL
BF75 0C 0C 0C		.BYTE	$C,$C,$C,$C,$E,$E,$E,$20
BF78 0C 0E 0E	
BF7B 0E 20   	
             	;
             	;
             	;
BF7D         	PHPOSB		; BOUNDS IN HITZYL
BF7D 00 00 00		.BYTE	0,0,0,2,4,6,8,$C
BF80 02 04 06	
BF83 08 0C   	
             	;
             	;
             	;
             	;
BF85         	PHODIF		; THINK
BF85 81 84 88		.BYTE	$81,$84,$88,$94
BF88 94      	
BF89         	ZYGIND		; THINK
BF89 80 10 10		.BYTE	$80,$10,$10,$10,$70,$70,$70,$10
BF8C 10 70 70	
BF8F 70 10   	
BF91         	INTSEQ		; THINK
BF91 04 04 00		.BYTE	4,4,0,0,0,1,0,0
BF94 00 00 01	
BF97 00 00   	
             	;
BF99         	ZYWARP		; THINK
BF99 3E 1E 10		.BYTE	$3E,$1E,$10,8,4,2,1,0,0,$81,$82,$84,$88,$90,$9E,$BE
BF9C 08 04 02	
BF9F 01 00 00	
BFA2 81 82 84	
BFA5 88 90 9E	
BFA8 BE      	
             	;
             	;
             	;
BFA9         	CLITAB		; LDTABS
BFA9 A6 AA AF		.BYTE	$A6,$AA,$FA,0,0,$B8,$5A,$FC,$5E,$90
BFAC 00 00 B8	
BFAF 5A FC 5E	
BFB2 90      	
             	;
             	;
BFB3         	JMASK		; HWARP SUB, USED FOR INITING TARG POSITIONS
BFB3 FF FF 3F		.BYTE	$FF,$FF,$3F,$0F,$3F,$7F,$FF,$FF
BFB6 0F 3F 7F	
BFB9 FF FF   	
             	;
             	;
BFBB         	JMPWHN		; TIMERS, WHEN EACH ZYLON TYPE SHOULD JUMP
BFBB 00 FF FF		.BYTE	0,$FF,$FF,$C0,$20
BFBE C0 20   	
             	;
BFC0         	JMPTAB		; TIMERS , JUMP VECTORS FOR ZYLONS
BFC0 F0 EF FF		.BYTE	$F0,$EF,$FF,15,16,17,1,$F1,0
BFC3 0F 10 11	
BFC6 01 F1 00	
             	;
BFC9         	PHVECT	; POHELP
BFC9 00 08 10		.BYTE	0,8,$10,$18,$28,$30,$38,$40
BFCC 18 28 30	
BFCF 38 40   	
             	;
             	;
             	;
BFD1         	COLTAB		; OBJCOL, CHROMA FOR EACH TYPE GRAPHIC
BFD1 50 00 20		.BYTE	$50,0,$20,$20,$20,0,$A0,0,0,$9F
BFD4 20 20 00	
BFD7 A0 00 00	
BFDA 9F      	
             	;
BFDB         	COLINT		; OBJCOL, INTENSITY PER XPOSH
BFDB 0E 0E 0E		.BYTE	$E,$E,$E,$C,$C,$C,$A,$A,$A,$8,$8,$8,$6,$6,$4,$4
BFDE 0C 0C 0C	
BFE1 0A 0A 0A	
BFE4 08 08 08	
BFE7 06 06 04	
BFEA 04      	
             	;
             	;
BFEB         	PHOTB2		; AUDIO, ATYPE3
BFEB 8A 8F 8D		.BYTE	$8A,$8F,$8D,$8B,$89,$87,$85,$83
BFEE 8B 89 87	
BFF1 85 83   	
BFF3         	PHOTB4		; AUDIO, AFREQ3
BFF3 00 04 01		.BYTE	0,4,1,4,1,4,1,4
BFF6 04 01 04	
BFF9 01 04   	
BFFB         	PHASE5
             	;
             	;
             	;
             	;
             	;
             	;		CARTRIDGE OPERATING CODES
             	;
             		*=$BFFC
BFFC 00      		.BYTE	0		; CARTRIDGE IN FLAG
BFFD 80      		.BYTE	$80		; RUN CARTRIDGE IMMEDIATELY
BFFE 4A A1   		.WORD	INIT		; START ADDR POINTER
             	;
C000         	PHASE9
             	;
             	;
             	;
             	;
             	;			RAM MAP
             		*=$280
0280         	RAMMAP			; MISC RAM STORAGE
0280         	DISPLY			; DISPLAY LIST RAM
             		*=*+128		; SEE EQUATES FOR INTERNAL LABELS
             	;
0300         	PHASE2
             	;
             		*=$300
0300         	PGRAPH
0300         	MGRAPH			; MISSLE GRAPHICS RAM
             		*=*+256
0400         	PGRAP0
             		*=*+256
0500         	PGRAP1
             		*=*+256
0600         	PGRAP2
             		*=*+256
0700         	PGRAP3
             		*=*+256
             	;
0800         	VCONL		; VERT CONVERT TABLE LO BYTE
             		*=*+100
0864         	VCONH		; VERT CONVERT TABLE HI BYTE
             		*=*+100
             		*=*+1		; BUFFER BYTE
08C9         	CHTRAM		; CHART RAM, MOW MANY ZYLONS IN EACH QUAD
             		*=*+128
0949         	DISCTL		; DISPLAY OF CONTRAL STATUS PANNEL
             		*=*+2
094B         	DVELOC		; DISP OF VELOC
             		*=*+2
             		*=*+3
0950         	DKILL		; DISP OF KILL
             		*=*+2
             		*=*+3
0955         	DENERG		; DISPLAY OF ENERGY
             		*=*+4
             		*=*+3
095C         	DCSTOR		; WHICH OBJ TRACKING
             		*=*+1
             	;			NEXT LINE
             		*=*+3
0960         	DTHETA		; DISPLAY OF THETA
             		*=*+3
             		*=*+3
0966         	DPHI			; DISPLAY OF PHI
             		*=*+3
             		*=*+3
096C         	DRHO			; DISPLAY OF RHO
             		*=*+4
             		*=*+1
             	;		NEXT LINE
0971         	DGALAC			; GALACTIC CHART INFO
             		*=*+12
097D         	DWENER			; DISPLAY WARP ENERGY
             		*=*+3
             		*=*+5
             	;		NEXT LINE
             		*=*+8
098D         	DTARG			; DISP OF TARGETS IN QUAD
             		*=*+1
             		*=*+4
0992         	DAMAGE		; DAMAGE CONTROL RAM, +0=PHOTONS,+1=ENGINES
             		*=*+6		; +2=SHIELDS,+3=COM,PUTER,+4=SECTOR SCAN
             				; +5=SUB-SPACE RADIO
             		*=*+1
             	;		NEXT LINE
             		*=*+10
09A3         	DSDATE			; DISP OF STAR DATE
             		*=*+5
             		*=*+5
09AD         	STRRAM		; RAM FOR STARS , OBJECTS  POSITIONS, ETC.
09AD         	XSIGN		; SIGN OF XPOS
             		*=*+RAMNUM
09DE         	YSIGN
             		*=*+RAMNUM
0A0F         	ZSIGN
             		*=*+RAMNUM
0A40         	XPOSH		; XPOS IN SPACE HI BYTE
             		*=*+RAMNUM
0A71         	YPOSH
             		*=*+RAMNUM
0AA2         	ZPOSH
             		*=*+RAMNUM
0AD3         	XPOSL		; XPOS IN SPACE LO BYTE
             		*=*+RAMNUM
0B04         	YPOSL
             		*=*+RAMNUM
0B35         	ZPOSL
             		*=*+RAMNUM
0B66         	XINCRE		; OBJECTS X DIRECTION VELOCITY
             		*=*+RAMNUM
0B97         	YINCRE
             		*=*+RAMNUM
0BC8         	ZINCRE
             		*=*+RAMNUM
0BF9         	VPOS		; VERT POS ON SCREEN
             		*=*+RAMNUM
0C2A         	HPOS		; HORIZ POS ON SCREEN
             		*=*+RAMNUM
0C5B         	OLDVER		; OLD VERT POSIT
             		*=*+RAMNUM
0C8C         	GINDEX		; TYPE OF GRAPHIC,		OBJECT
0C8C         	OLDHOR		; OLD HORIZ POSIT		STARS
             		*=*+RAMNUM
0CBD         	OLDNUM		; PREVIOUS NUMBER OF BYTES STORED		OBJECT
0CBD         	OLDBYT		; OLD BYTE IN RAM MAP				STARS
             		*=*+RAMNUM
0CEE         	NUMBYT		; HOW MANY BYTES TO STORE		OBJECT
0CEE         	STRBYT		; THE BYTE TO STORE		STARS
             		*=*+RAMNUM
0D1F         	MESAGE		; DISPLAY OF MESSAGE RAM
             		*=*+20
             		*=*+2		; BUFFER ZONE
             	;
0D35         	CHTDIS		; CHAR GRAPHICS PNTR FO GALCHT
             		*=*+180
             	;
0DE9         	PTAB		; X80 SCALER TABLE
             		*=*+256
0EE9         	BCDCON		; BINARY TO BCD TABLE
             		*=*+256
             	;
0FE9         	PHASE7
             	;
             			*=$1000
1000         	MEMMAP			; SCREEN MAP RAM
             		*=*+4096
2000         	MEMEND
2000         	PHASE3
             	;
             	;			END PROGRAM
             		.END
