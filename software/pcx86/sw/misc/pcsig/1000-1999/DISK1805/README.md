---
layout: page
title: "PC-SIG Diskette Library (Disk #1805)"
permalink: /software/pcx86/sw/misc/pcsig/1000-1999/DISK1805/
machines:
  - id: ibm5170
    type: pcx86
    config: /machines/pcx86/ibm/5170/cga/1024kb/rev3/machine.xml
    diskettes: /machines/pcx86/diskettes.json,/disks/pcsigdisks/pcx86/diskettes.json
    autoGen: true
    autoMount:
      B: "PC-SIG Library Disk #1805"
    autoType: $date\r$time\rB:\rDIR\r
---

{% include machine.html id="ibm5170" %}

{% comment %}info_begin{% endcomment %}

## Information about "AMORT70"

    This loan amortization program also specializes notes.  You can
    calculate monthly or weekly home or personal loan amortization, and
    daily, weekly, or monthly interest on notes with a set repayment
    amount.
    
    Both the loan and note menus will walk you through the numbers by
    prompting you for information.  Who is the report prepared for?  What is
    the amount?  The interest rate?  The period?  The calculations are fast
    and easy to understand.  Great for the professional who does a lot of
    calculating.
{% comment %}info_end{% endcomment %}

{% comment %}samples_begin{% endcomment %}

## AMORTIZE.DOC

{% raw %}
```



                        AMORTIZE.DOC  for  AMORT70_.EXE
                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


             AMORT70_.EXE  is a multi-part loan amortization program.


         ----------------------------------------------------------------

         COPYRIGHT NOTICE:

           Copyright (c) 1983,84,85,86,89  by  Burgess Enterprises Ltd. 

                       *** ALL RIGHTS RESERVED WORLDWIDE ***

         ----------------------------------------------------------------         

         LICENSE AGREEMENT:
 
         You may copy and distribute this program freely, provided that:

            1 -  There are no charges other than duplication fees
                      ($8.00 limit).

            2 -  It is distributed unaltered and with all 20 files.

         As this is a user supported program, a contribution would be 
         appreciated if you find this program useful  ($20 suggested).
         You will be placed on our mailing list and be sent a disk 
         containing the current version of AMORT.EXE. 

         ----------------------------------------------------------------


         NECESSARY FILES:   RUN.BAT        VIDPOP.COM     AMORT70_.EXE
                            AMORT.LIB

         OPTIONAL FILES:    AMORTIZE.DOC   READ.ME        AMORT52B.EXE
                            CAMORT.LIB     CRUN.BAT

         ----------------------------------------------------------------


         ----------------------------------------------------------------

 
         SYSTEM REQUIREMENTS:  IBM-PC, XT or AT   OR   100% Compatibles
                               PC-DOS or MS-DOS 2.0 or Higher
                               256k Ram Memory
                               1 - 360k Disk Drive
                               Monochrome or Color Graphics Monitor

   
         ----------------------------------------------------------------


         VIDPOP(tm) Screen Utility by:  The Research Group
                  (415)571-5019         88 South Linden Ave.
                                        South San Francisco, CA  94080


         ----------------------------------------------------------------
         

         TRADEMARKS:  Saywhat!, Vidpop, The Research Group are Trademarks
                      of The Research Group.
                      IBM-PC, XT, AT, PC-DOS are Trademarks of IBM.
                      MS-DOS is a Trademark of Microsoft.
        

         ----------------------------------------------------------------

         DISCLAIMER:

                      BURGESS ENTERPRISES LTD. makes no representations or
                      warranties with respect to the fitness of this 
                      program for any particular purpose.  


         ----------------------------------------------------------------




                              MAIN MENU CHOICES



         ----------------------------------------------------------------
         
         TYPE  1:  Standard Home or Personal Loan Amortization  (Monthly)
         TYPE  2:    (same only Weekly)
         TYPE  3:  Note interest Calculator   (Daily)
         TYPE  4:  Note w/ set repayment amount  (Monthly)
         TYPE  5:    (same only Weekly)

         ----------------------------------------------------------------






         Data Entry:     (Very similar for all menu choices)
         ~~~~~~~~~~~

         ---  You may answer any < Y or N > question with a default
                    'NO'  by just hitting the <ENTER> key.


         (1)  Prepared For:    If any typing error is made you can now use
                               the backspace key.  However, you can also   
                               restart the entry by hiting the escape key 
                               twice, then a return.

         (2)  Loan Amount:  Do not use $ or symbols in front of the number.
                 or         Do not use any commas in the number.
              Payment       The amount must be greater than 0 and less than
                            one million.

         (3)  Period:    The length of the loan must be greater than 0 and 
                         less than 40 years.

         (4)  Interest:   In this program, interest may be entered as either
                          a percentage or a rate. Twelve percent could be
                          entered as either   12 [ENTER]  or  .12 [ENTER].

         --------------------------------------------------------------------


                           Main Menu Choices
                         ---------------------
                   ****   Plus All Sub Choices   ****



     --------------------------------------------------------------------

     Choice [1]  Mortgage or Installment Loans (Monthly)

        Data Entry: <1> Who is Report Prepared For?
                    <2> Enter Interest Rate  :
                    <3> Enter the Period in Years:
                    <4> Do you want to enter (L)oan or (P)ayment Amount?
                        If "P": (a) Enter Payment Amount
                        If "L": (a) Enter Loan Amount

         Options:   <5> Do you Wish to Change any Variables?
                        If Yes: (a) Change Loan Amount
                                (b) Change Payment Amount
                                (c) Change Period
                                (d) Change Interest Rate
                    
                    <6> Do you want Output to go to (P)rinter,
                           (D)isk File or Monitor (P,D,M)?
                        If 'P': (a) Printer must be turned on &
                                    on line.
                        If 'D': (b) Output is written to a Disk File
                                    named "Amort.prn".
                                    If you wish to keep this file, rename
                                    it before you use the program to
                                    save another amortization.
                        If 'M' or [ENTER]:  (c) Output is sent to the
                                                monitor.

                    <7> Do You want a Complete Amortization?
                        if Yes: (a) What year does this loan start?
                                (b) What month number is the first payment?

                    <8> Do you want a Period Summary?
                        If Yes: (a) Enter the Starting Payment number.
                                (b) Enter the Ending Payment number.

                    <9> Do you wish to return to the Main Menu?

     --------------------------------------------------------------------



     --------------------------------------------------------------------

     Choice [2]  Mortgage or Installment Loans (Weekly)

        Data Entry: <1> Who is Report Prepared For?
                    <2> Enter Loan Amount:
                    <3> Enter Interest Rate:
                    <4> Enter the Period in Weeks:

        Options:    <5> Do you want Output to go to (P)rinter,
                           (D)isk File or Monitor (P,D,M)?
                        If 'P': (a) Printer must be turned on &
                                    on line.
                        If 'D': (b) Output is written to a Disk File
                                    named "Amort.prn".
                                    If you wish to keep this file, rename
                                    it before you use the program to
                                    save another amortization.
                        If 'M' or [ENTER]:  (c) Output is sent to the
                                                monitor.

                    <6> Do You want a Complete Amortization?

                    <7> Do you want a Period Summary?
                        If Yes: (a) Enter the Starting Payment number.
                                (b) Enter the Ending Payment number.

                    <8> Do you wish to return to the Main Menu?

     --------------------------------------------------------------------


     --------------------------------------------------------------------

     Choice [3]  DAILY NOTE  --  Interest Calculator

        Data Entry: <1> Who is Report Prepared For?
                    <2> Enter Loan Amount:
                    <3> Enter Interest Rate:
                    <4> Enter the Period in Days:

        Options:    <5> Do you want Output to go to (P)rinter,
                           (D)isk File or Monitor (P,D,M)?
                        If 'P': (a) Printer must be turned on &
                                    on line.
                        If 'D': (b) Output is written to a Disk File
                                    named "Amort.prn".
                                    If you wish to keep this file, rename
                                    it before you use the program to
                                    save another amortization.
                        If 'M' or [ENTER]:  (c) Output is sent to the
                                                monitor.

                    <6> Do you wish to return to the Main Menu?

     --------------------------------------------------------------------


     --------------------------------------------------------------------

     Choice [4]  NOTE  -  Set Principal Repayment  (Monthly)

        Data Entry: <1> Who is Report Prepared For?
                    <2> Enter Loan Amount:
                    <3> Enter Interest Rate:
                    <4> Enter the Period in Years:

        Options:    <5> Do you want Output to go to (P)rinter,
                           (D)isk File or Monitor (P,D,M)?
                        If 'P': (a) Printer must be turned on &
                                    on line.
                        If 'D': (b) Output is written to a Disk File
                                    named "Amort.prn".
                                    If you wish to keep this file, rename
                                    it before you use the program to
                                    save another amortization.
                        If 'M' or [ENTER]:  (c) Output is sent to the
                                                monitor.

                    <6> Do You want a Complete Amortization?

                    <7> Do you wish to return to the Main Menu?

     --------------------------------------------------------------------


     --------------------------------------------------------------------

     Choice [5]  NOTE  -  Set Principal Repayment  (Weekly)

        Data Entry: <1> Who is Report Prepared For?
                    <2> Enter Loan Amount:
                    <3> Enter Interest Rate:
                    <4> Enter the Period in Weeks:

        Options:    <5> Do you want Output to go to (P)rinter,
                           (D)isk File or Monitor (P,D,M)?
                        If 'P': (a) Printer must be turned on &
                                    on line.
                        If 'D': (b) Output is written to a Disk File
                                    named "Amort.prn".
                                    If you wish to keep this file, rename
                                    it before you use the program to
                                    save another amortization.
                        If 'M' or [ENTER]:  (c) Output is sent to the
                                                monitor.

                    <6> Do You want a Complete Amortization?

                    <7> Do you wish to return to the Main Menu?

     --------------------------------------------------------------------
 
                             (Sample - Type 1) <Full Amortization>
          ------------------------------------------------------------


                  Direct Reduction Loan Amortization  (Monthly)

          Date:  8-07-86      Prepared For: Eric Burgess






















































                                   (Sample - Type 1)  <Period Summary>
         -------------------------------------------------------------

                  Direct Reduction Loan Amortization  (Monthly)

          Date:  8-08-86      Prepared For: Eric Burgess
































          Summary for Payments  7 to 18

          Total Interest Paid       65.77
          Total Principal Paid     499.11


                                 (Sample - Type 2)  <Full Amortization> 
          -------------------------------------------------------------


                  Direct Reduction Loan Amortization  (Weekly )

          Date:  8-08-86      Prepared For: Eric Burgess






























                                   (Sample - Type 2)  <Period Summary>
          ------------------------------------------------------------

                  Direct Reduction Loan Amortization  (Weekly )

          Date:  8-08-86      Prepared For: Eric Burgess






























          Summary for Payments  1 to 10

          Total Interest Paid       12.74
          Total Principal Paid    1000.00



                                                      (Sample - Type 3)
          --------------------------------------------------------------








                   Daily Note -- Interest Calculator             

          Date:  8-07-86      Prepared For: Eric Burgess

















                                        (**) 360 Day Banking Year



                                                      (Sample - Type 4)
          --------------------------------------------------------------

                   NOTE AMORTIZATION - Fixed Principal (Monthly)

          Date:  8-08-86     Prepared For: Eric Burgess




























                                                      (Sample - Type 5)
          --------------------------------------------------------------

                   NOTE AMORTIZATION - Fixed Principal (Weekly )

          Date:  8-08-86     Prepared For: Eric Burgess
































                       AMORT70_.EXE  REGISTRATION  FORM
                     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


         Name ___________________________________
         
         Address  _______________________________

                  _______________________________
           
           City   ___________________ ST ______   Zip_______________


        Your Phone Number: _____________________



        **************************************************************
        
        Amort  Version #  Shown  on  First  Screen  ___________
                                                     EG: 7.0c
        **************************************************************



        Where did you find our program? ______________________________

           If bulletin board - Phone#   ______________________________
                              Address   ______________________________
                                        ______________________________
                                        ______________________________



        Any Suggestions or Comments?__________________________________
        ______________________________________________________________
        ______________________________________________________________
        ______________________________________________________________
        ______________________________________________________________
        ______________________________________________________________
        ______________________________________________________________


                Suggested Contribution ($20.00)     ______________
                Sales Tax  (NYS Residents Only)     ______________
                                      Total         ______________
 

          Please send with contribution to:  Burgess Enterprises Ltd.
                                             Attn:  Eric Burgess
                                             PO Box 524
                                             Plattsburgh, NY   12901


```
{% endraw %}

## FILE1805.TXT

{% raw %}
```
Disk No: 1805                                                           
Disk Title: Amort70                                                     
PC-SIG Version: S1                                                      
                                                                        
Program Title: Amort70                                                  
Author Version: 7.0J                                                    
Author Registration: $20.00                                             
Special Requirements: None.                                             
                                                                        
This loan amortization program also specializes notes.  You can         
calculate monthly or weekly home or personal loan amortization, and     
daily, weekly, or monthly interest on notes with set repayment amount.  
                                                                        
Both the loan and note menus will walk you through the numbers by       
prompting you for information.  Who is the report prepared for?  What is
the amount?  The interest rate?  The period?  The calculations are fast 
and easy to understand.  Great for the professional who does a lot of   
calculating.                                                            
                                                                        
PC-SIG                                                                  
1030D East Duane Avenue                                                 
Sunnyvale  Ca. 94086                                                    
(408) 730-9291                                                          
(c) Copyright 1989 PC-SIG, Inc.                                         
```
{% endraw %}

## GO.TXT

{% raw %}
```
╔═════════════════════════════════════════════════════════════════════════╗
║                 <<<<  Disk #1805  AMORT70  >>>>                         ║
╠═════════════════════════════════════════════════════════════════════════╣
║ To start program, type: RUN                                             ║
║                                                                         ║
║ To print documentation, type: COPY AMORTIZE.DOC PRN                     ║
╚═════════════════════════════════════════════════════════════════════════╝
```
{% endraw %}

{% comment %}samples_end{% endcomment %}

### Directory of PC-SIG Library Disk #1805

     Volume in drive A has no label
     Directory of A:\

    AMORT    LIB     10270   3-30-89   1:16p
    AMORT52B EXE     29184   4-03-89   8:31a
    AMORT70J EXE     28672   8-11-86  11:59a
    AMORTIZE DOC     25238   8-07-89   7:09a
    CAMORT   LIB     10450   5-19-89   1:39p
    CRUN     BAT       255   5-19-89   1:41p
    FILE1805 TXT      1777  12-20-89   4:16p
    GO       BAT        38   1-01-80   1:37a
    GO       TXT       540   1-01-80   7:52a
    READ     ME       2857   8-07-89   7:08a
    RUN      BAT       249   5-13-87   2:02p
    VIDPOP   COM     27328   6-18-87   2:58p
           12 file(s)     136858 bytes
                           19968 bytes free