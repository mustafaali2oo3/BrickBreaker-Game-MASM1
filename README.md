# BrickBreaker-Game-MASM1
A solo game created in assembly , using Microsoft macro assembler x86. Consisting of different levels, power ups and special bombs.


INCLUDE Irvine32.inc
includelib winmm.lib

.data

    PlaySound PROTO,
    pszSound:PTR BYTE,       ; function from winmm.lib to play music file
    hmod:DWORD, 
    fdwSound:DWORD
                    
    ; level 1
    game_screen1   db "||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                    aaaa aaaa aaaa aaaa      aaaa aaaa aaaa aaaa                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                               aaaa aaaa aaaa aaaa                aaaa aaaa aaaa aaaa                               ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                          aaaa aaaa aaaa aaaa aaaa aaaa      aaaa aaaa aaaa aaaa aaaa aaaa                          ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                     aaaa aaaa aaaa aaaa aaaa aaaa aaaa aaaa aaaa aaaa aaaa aaaa aaaa dddd aaaa                     ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||",0Ah
                   db "|| SCORE :      || LIVES :      ||                                                                                    ||",0Ah
                   db "||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||",0
     
    ; level 2
    game_screen2   db "||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                     |||| bbbb bbbb bbbb bbbb bbbb bbbb bbbb bbbb bbbb bbbb bbbb bbbb bbbb ||||                     ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                     bbbb                                                                  bbbb                     ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                     bbbb                                                                  bbbb                     ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                     |||| bbbb bbbb dddd bbbb bbbb bbbb bbbb bbbb bbbb bbbb bbbb bbbb bbbb ||||                     ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||",0Ah
                   db "|| SCORE :      || LIVES :      ||                                                                                    ||",0Ah
                   db "||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||",0

    ; level 3
    game_screen3   db "||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                     cccc cccc cccc cccc cccc cccc cccc cccc cccc cccc cccc cccc cccc cccc cccc                     ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                     cccc      cccc      cccc      cccc      cccc      cccc      cccc      cccc                     ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                     cccc cccc      cccc      cccc      cccc      cccc      cccc      cccc cccc                     ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                     cccc cccc cccc cccc cccc cccc cccc cccc cccc cccc eeee cccc cccc cccc cccc                     ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||",0Ah
                   db "|| SCORE :      || LIVES :      ||                                                                                    ||",0Ah
                   db "||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||",0

    ; win screen
    ending_screen  db "##====================================================================================================================##",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                          _____ _   _  _____   _____ _   _______                                    ||",0Ah
                   db "||                                         |_   _| | | ||  ___| |  ___| \ | |  _  \                                   ||",0Ah
                   db "||                                           | | | |_| || |__   | |__ |  \| | | | |                                   ||",0Ah
                   db "||                                           | | |  _  ||  __|  |  __|| . ` | | | |                                   ||",0Ah
                   db "||                                           | | | | | || |___  | |___| |\  | |/ /                                    ||",0Ah
                   db "||                                           \_/ \_| |_/\____/  \____/\_| \_/___/                                     ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "##====================================================================================================================##",0    
                   
     pause_screen  db "##====================================================================================================================##",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||         /$$$$$$$  /$$$$$$$  /$$$$$$  /$$$$$$  /$$   /$$ /$$$$$$$  /$$$$$$$  /$$$$$$$$  /$$$$$$  /$$   /$$          ||",0Ah
                   db "||         | $$__  $$| $$__  $$|_  $$_/ /$$__  $$| $$  /$$/| $$__  $$| $$__  $$| $$_____/ /$$__  $$| $$  /$$/         ||",0Ah
                   db "||         | $$  \ $$| $$  \ $$  | $$  | $$  \__/| $$ /$$/ | $$  \ $$| $$  \ $$| $$      | $$  \ $$| $$ /$$/          ||",0Ah
                   db "||         | $$$$$$$ | $$$$$$$/  | $$  | $$      | $$$$$/  | $$$$$$$ | $$$$$$$/| $$$$$   | $$$$$$$$| $$$$$/           ||",0Ah
                   db "||         | $$__  $$| $$__  $$  | $$  | $$      | $$  $$  | $$__  $$| $$__  $$| $$__/   | $$__  $$| $$  $$           ||",0Ah
                   db "||         | $$  \ $$| $$  \ $$  | $$  | $$    $$| $$\  $$ | $$  \ $$| $$  \ $$| $$      | $$  | $$| $$\  $$          ||",0Ah
                   db "||         | $$$$$$$/| $$  | $$ /$$$$$$|  $$$$$$/| $$ \  $$| $$$$$$$/| $$  | $$| $$$$$$$$| $$  | $$| $$ \  $$         ||",0Ah
                   db "||         |_______/ |__/  |__/|______/ \______/ |__/  \__/|_______/ |__/  |__/|________/|__/  |__/|__/  \__/         ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||         HIGHSCORES                                                                                                 ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                            PRESS P TO UNPAUSE      ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                            PRESS X TO GIVE UP      ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "||                                                                                                                    ||",0Ah
                   db "##====================================================================================================================##",0     


    cheatbool db 0   ; bool that shows if skipping levels cheat on/off
    currentlevel db 0
    brickcount dd 0
    score dd 0
    lives db 3

    ; all paddle player variables
    paddle db "=====",0     ; string that stores player paddle
    paddle_x db "     ",0   ; to print over paddle when clearing it (for moving)
    xPos BYTE 59
    yPos BYTE 25
    paddlecolor dd yellow
    paddlelength db 5

    ; all primary ball variables
    ballx db 60
    bally db 23
    balldir db 1   ; ball direction
    ballspeed dd 500

    ; all secondary ball (powerup) variables
    secondballbool db 0 ; if multiball powerup collected
    secondballx db 60
    secondbally db 23
    secondballdir db 4
    lastmove2 dd 0 ; stores time of last movement (uses ballspeed to emulate speed)

    lastmove dd 0
    brickhitx db 0 ; stores x of collided brick/wall
    brickhity db 0
    brick1color dd green+(green*16)          ; single hit brick
    brick2color dd yellow+(yellow*16)        ; 2 hit brick
    brick3color dd red+(red*16)              ; 3 hit brick
    brick4color dd blue+(blue*16)            ; power up spawn random brick
    brick5color dd brown+(brown*16)          ; bomb brick special

    ; all powerup variables
    PowerUpSpawned db 0 ; bool if powerup spawned
    PowerUpType db 0    ; randomly selected powerup type
    PowerUpx db 0       
    PowerUpy db 0
    lastPowerMove dd 0  ; emulate speed of powerup dropping
    PoweredUpBool db 0  ; whether ball powered up

    ; all variables to help with bomb explosion
    randomx db 0
    randomy db 0
    explodednum db 0
    explodedbool db 0

    inputChar BYTE 0
    current_level_screen dd 0

    ; all menu strings/variables
    border BYTE "||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||||",0
    border1 BYTE "|",0ah,0
    border2 BYTE "|",0
    border3 BYTE "----------------------------",0
    T byte ?
    newT byte ?
    xheadingPos db ?
    yheadingPos db ?
    StartString db "PRESS ENTER TO START", 0
    OptionString db "PRESS I FOR OPTIONS", 0
    ExitString db "PRESS X TO QUIT", 0
    MuteString db "PRESS M FOR MUTE    ", 0
    CheatString db "PRESS C FOR CHEATS ", 0
    InputNameString db "ENTER NAME:", 0
    playerString db "PLAYER:", 0
    player_name byte 11 dup(?),0
    nameSize db ?

    heading db " /$$$$$$$  /$$$$$$$  /$$$$$$  /$$$$$$  /$$   /$$ /$$$$$$$  /$$$$$$$  /$$$$$$$$  /$$$$$$  /$$   /$$",0
            db "| $$__  $$| $$__  $$|_  $$_/ /$$__  $$| $$  /$$/| $$__  $$| $$__  $$| $$_____/ /$$__  $$| $$  /$$/",0
            db "| $$  \ $$| $$  \ $$  | $$  | $$  \__/| $$ /$$/ | $$  \ $$| $$  \ $$| $$      | $$  \ $$| $$ /$$/ ",0
            db "| $$$$$$$ | $$$$$$$/  | $$  | $$      | $$$$$/  | $$$$$$$ | $$$$$$$/| $$$$$   | $$$$$$$$| $$$$$/  ",0
            db "| $$__  $$| $$__  $$  | $$  | $$      | $$  $$  | $$__  $$| $$__  $$| $$__/   | $$__  $$| $$  $$  ",0
            db "| $$  \ $$| $$  \ $$  | $$  | $$    $$| $$\  $$ | $$  \ $$| $$  \ $$| $$      | $$  | $$| $$\  $$ ",0
            db "| $$$$$$$/| $$  | $$ /$$$$$$|  $$$$$$/| $$ \  $$| $$$$$$$/| $$  | $$| $$$$$$$$| $$  | $$| $$ \  $$",0 
            db "|_______/ |__/  |__/|______/ \______/ |__/  \__/|_______/ |__/  |__/|________/|__/  |__/|__/  \__/",0 

    ; function to create/open file
    CreateFile PROTO,           ; create new file
    pFilename:PTR BYTE,     ; ptr to filename
    accessMode:DWORD,       ; access mode
    shareMode:DWORD,        ; share mode
    lpSecurity:DWORD,       ; can be NULL
    howToCreate:DWORD,      ; how to create the file
    attributes:DWORD,       ; file attributes
    htemplate:DWORD         ; handle to template file

    ; function to read file
    ReadFile PROTO,           ; read buffer from input file
    fileHandle:DWORD,     ; handle to file
    pBuffer:PTR BYTE,     ; ptr to buffer
    nBufsize:DWORD,       ; number bytes to read
    pBytesRead:PTR DWORD, ; bytes actually read
    pOverlapped:PTR DWORD ; ptr to asynchronous info


    ; all music variables
    SND_FILENAME DWORD 00020000h
    SND_LOOP DWORD  00000008h
    SND_ASYNC DWORD 00000001h
    file BYTE ".\gamemusic.wav" , 0

    ; all filehandling variables
    filehandling_array byte 10 dup(15 dup('-'))
    highscores_file_handle dword ?
    highscores_file_name byte "highscores.txt",0
    temp_filehandling_score dd 0
    temp_filehandling_array byte 15 dup('-')
    temp_filehandling_array2 byte 15 dup('-')
    temp_index dd 0
    top5_stats_str byte 17 dup('-'),0,0
    temp byte ?                                                                       
                                           

.code
main PROC

    ; if highscores file exists, open it. Otherwise create
    call MakeHighScoreFile
    ; Read it into an array
    call ReadHighScoreFile

    ;play sound
    mov eax, SND_FILENAME  
    or eax, SND_LOOP       
    or eax, SND_ASYNC 
    invoke PlaySound, addr file,0,eax

    ;menu 
    call headingPrint
    
    NextLevel:
        inc currentlevel
        call InitializeLevel
        call Randomize
    BackToGame:
        call DrawGameScreen
        call DrawPlayer

    gameLoop:

    cmp lives,0
    je GameOver

        cmp brickcount,0
        jbe NextLevel

        call MoveBall
        call MoveBall2
        call MovePowerUp
        call DrawHUD

        call ReadKey
        jz gameLoop 
        mov inputChar,al

        ; exit game if user types 'x':
        cmp inputChar,"x"
        je exitGame

        cmp inputChar,"a"
        je moveLeft

        cmp inputChar,"d"
        je moveRight

        cmp inputChar,"c"
        je cheatpressed

        cmp inputChar,"p"
        je paused

        jmp keep_looping_gameloop

        moveLeft:
            cmp xPos,2
            je keep_looping_gameloop
        

                call UpdatePlayer
                dec xPos
                call DrawPlayer
                jmp keep_looping_gameloop

        moveRight:
            mov al,118
            sub al,paddlelength
            cmp xPos,al
            je keep_looping_gameloop
        
                call UpdatePlayer
                inc xPos
                call DrawPlayer
                jmp keep_looping_gameloop

        cheatpressed:
            cmp cheatbool,1
            je NextLevel
            jmp keep_looping_gameloop

        paused:
            call DrawPauseScreen

            pauseloop:
                call ReadKey
                jz pauseloop 
                mov inputChar,al

                cmp inputChar,'p'
                je BackToGame

                cmp inputChar,'x'
                je exitGame

    keep_looping_gameloop:

        cmp lives,0
        jbe exitGame

        jmp gameLoop

    exitGame:
        call GameOver

    exit
main ENDP

DrawPlayer PROC
    ; draw player at (xPos,yPos):
    mov eax,paddlecolor ;(blue*16)
    call SetTextColor
    mov dl,xPos
    mov dh,yPos
    call Gotoxy
    mov edx,offset paddle
    call WriteString
    ret
DrawPlayer ENDP

UpdatePlayer PROC
    mov eax,black
    call settextcolor
    mov dl,xPos
    mov dh,yPos
    call Gotoxy
    mov edx,offset paddle_x
    call WriteString
    ret
UpdatePlayer ENDP

DrawBall PROC
    mov eax,magenta
    call SetTextColor
    mov dl,ballx
    mov dh,bally
    call Gotoxy
    mov al,'0'
    call WriteChar
    ret
DrawBall ENDP

UpdateBall PROC
    mov eax,black
    call SetTextColor
    mov dl,ballx
    mov dh,bally
    call Gotoxy
    mov al,' '
    call WriteChar
    ret
UpdateBall ENDP

DrawPowerUp PROC
    mov eax,green
    call SetTextColor
    mov dl,PowerUpx
    mov dh,PowerUpy
    call Gotoxy
    mov al,PowerUpType
    call WriteChar
    ret
DrawPowerUp ENDP

UpdatePowerUp PROC
    mov eax,edi
    call SetTextColor
    mov dl,PowerUpx
    mov dh,PowerUpy
    call Gotoxy
    mov al,cl
    call WriteChar
    ret
UpdatePowerUp ENDP

MovePowerUp PROC

    cmp PowerUpSpawned,0
    je MovePowerUp_exit

    call getMseconds
    mov ebx,eax
    sub eax,lastPowerMove

    cmp eax,ballspeed
    jae movepowerup_start

    ret

    movepowerup_start:

        cmp PowerUpy,25
        jbe notexpired

        mov PowerUpSpawned,0
        call UpdatePowerUp
        ret

        notexpired:
        mov lastPowerMove,ebx

    mov esi,current_level_screen
    movzx edx,PowerUpy
    imul edx,121
    add esi,edx
    movzx edx,PowerUpx
    add esi,edx
    mov cl,byte ptr [esi]

    cmp cl,'a'
    je color_a1 
    cmp cl,'b'
    je color_b1 
    cmp cl,'c'
    je color_c1 
    cmp cl,'d'
    je color_d1 
    cmp cl,'e'
    je color_e1 

    mov edi,black
    jmp colorfound

    color_a1:
        mov edi,brick1color
        jmp colorfound
    color_b1:
        mov edi,brick2color
        jmp colorfound
    color_c1:
        mov edi,brick3color
        jmp colorfound
    color_d1:
        mov edi,brick4color
        jmp colorfound
    color_e1:
        mov edi,brick5color
        jmp colorfound

    colorfound:

        call UpdatePowerUp
        inc PowerUpy
        call DrawPowerUp

        mov cl,PowerUpx
        mov ch,PowerUpy

        cmp yPos,ch
        jne MovePowerUp_exit
        cmp xPos,cl
        ja MovePowerUp_exit
        sub cl,paddlelength
        inc cl
        cmp xPos,cl
        jb MovePowerUp_exit

        mov PowerUpSpawned,0
        cmp PowerUpType,'s'
        je enable_specball
        cmp PowerUpType,'m'
        je enable_multiball
        enable_specball:
            mov PoweredUpBool,1
            jmp MovePowerUp_exit
        enable_multiball:
            mov secondballbool,1
            jmp MovePowerUp_exit


        MovePowerUp_exit:
ret
MovePowerUp ENDP

DrawPauseScreen PROC

    call clrscr

    mov eax,yellow
    call settextcolor

    mov dl,0
    mov dh,0
    call GoToXY

    mov edx,offset pause_screen
    call writestring

    mov ecx,10
    mov dh,14
    mov temp,dh
    mov esi,offset filehandling_array
    loop6:
    push ecx
    call stats_array_maker
    pop ecx
    mov dh,temp
    mov dl,10
    call Gotoxy
    mov edx,OFFSET top5_stats_str
    call WriteString
    inc temp
    add esi,15
    loop loop6


ret
DrawPauseScreen ENDP

DrawGameScreen PROC

    mov eax,yellow
    call SetTextColor

    mov dl,0
    mov dh,0
    call GoToXY
    mov edx,current_level_screen
    call writestring

    mov esi,current_level_screen
    mov ecx,30
    mov al,0
    mov ah,0
    mov edi,0

    slash_counter_loop_outer:

        mov ebx,ecx
        mov ecx,120

        slash_counter_loop_inner:
            mov dl,'a'
            cmp [esi],dl
            je color_a 
            mov dl,'b'
            cmp [esi],dl
            je color_b 
            mov dl,'c'
            cmp [esi],dl
            je color_c 
            mov dl,'d'
            cmp [esi],dl
            je color_d 
            mov dl,'e'
            cmp [esi],dl
            je color_e 
            jne slash_counter_loop_inner_cont

            color_a:
                mov edi,brick1color
                jmp color_brick
            color_b:
                mov edi,brick2color
                jmp color_brick
            color_c:
                mov edi,brick3color
                jmp color_brick
            color_d:
                mov edi,brick4color
                jmp color_brick
            color_e:
                mov edi,brick5color
                jmp color_brick

            color_brick:
                mov dl,al
                mov dh,ah
                call Gotoxy
                mov eax,edi
                call SetTextColor
                mov al,byte ptr [esi]
                call WriteChar

                mov al,dl
                mov ah,dh

        slash_counter_loop_inner_cont:
        inc esi
        inc al
        LOOP slash_counter_loop_inner

        mov ecx,ebx
        mov al,0
        inc ah
        inc esi

    LOOP slash_counter_loop_outer

ret
DrawGameScreen ENDP

DrawHUD PROC

    mov eax , yellow
    call settextcolor

    mov dl,11
    mov dh,28
    call gotoxy
    mov eax,score
    call writeint

    mov dl,27
    mov dh,28
    call gotoxy
    movzx eax,lives
    call writeint

ret
DrawHUD ENDP

MoveBall PROC

    call getMseconds
    mov ebx,eax
    sub eax,lastmove

    cmp eax,ballspeed
    jae moveball_start

    ret

    moveball_start:

        cmp bally,26
        jne nodeath
        
        ; death 

        dec lives
        call UpdateBall
        mov ballx,60 
        mov bally,23
        mov balldir,1
        call DrawBall
        mov eax,100
        call delay
        jmp MoveBall_exit

        nodeath:
        mov lastmove,ebx
        call CheckBallCollision

        check_collision:
            cmp dl,' '
            je nocollision
            cmp dl,'|'
            je change_dir

            call BrickHit

            cmp poweredupbool,1
            je MoveBall_exit

            change_dir:
                call ChangeDirection
                jmp MoveBall_exit

            nocollision:
                cmp balldir,1
                je upright_m
                cmp balldir,2
                je downright_m
                cmp balldir,3
                je downleft_m
                cmp balldir,4
                je upleft_m

            
                upright_m:
                    call UpdateBall
                    inc ballx
                    dec bally
                    call DrawBall
                    jmp MoveBall_exit
                downright_m:
                    call UpdateBall
                    inc ballx
                    inc bally
                    call DrawBall
                    jmp MoveBall_exit
                downleft_m:
                    call UpdateBall
                    dec ballx
                    inc bally
                    call DrawBall
                    jmp MoveBall_exit
                upleft_m:
                    call UpdateBall
                    dec ballx
                    dec bally
                    call DrawBall
                    jmp MoveBall_exit
            

MoveBall_exit:
ret
MoveBall ENDP

ChangeDirection PROC
pushad

    sub esi,121
    mov dl,byte ptr [esi]

    cmp bally,1
    je upperhit

    cmp dl,' '
    je brickshit

    wallhit:
        cmp balldir,1
        je upright_ch
        cmp balldir,2
        je downright_ch
        cmp balldir,3
        je downleft_ch
        cmp balldir,4
        je upleft_ch

        upright_ch:
            mov balldir,4
            jmp ChangeDirection_exit
        downright_ch:
            mov balldir,3
            jmp ChangeDirection_exit
        downleft_ch:
            mov balldir,2
            jmp ChangeDirection_exit
        upleft_ch:
            mov balldir,1
            jmp ChangeDirection_exit 

    brickshit:
        cmp balldir,1
        je upright_cha
        cmp balldir,2
        je downright_cha
        cmp balldir,3
        je downleft_cha
        cmp balldir,4
        je upleft_cha

        upright_cha:
            mov balldir,2
            jmp ChangeDirection_exit
        downright_cha:
            mov balldir,1
            jmp ChangeDirection_exit
        downleft_cha:
            mov balldir,4
            jmp ChangeDirection_exit
        upleft_cha:
            mov balldir,3
            jmp ChangeDirection_exit 

    upperhit:
        cmp balldir,1
        je upright_chau
        cmp balldir,4
        je upleft_chau

        upright_chau:
            mov balldir,2
            jmp ChangeDirection_exit
        upleft_chau:
            mov balldir,3
            jmp ChangeDirection_exit 
        
   

ChangeDirection_exit:
popad
ret
ChangeDirection ENDP

CheckBallCollision PROC

    mov dl,ballx
    mov brickhitx,dl
    mov dl,bally
    mov brickhity,dl
    
    cmp balldir,1
    je upright
    cmp balldir,2
    je downright
    cmp balldir,3
    je downleft
    cmp balldir,4
    je upleft

    upright:
        mov esi,current_level_screen
        movzx edx,bally
        dec edx
        dec brickhity
        imul edx,121
        add esi,edx
        movzx edx,ballx
        inc edx
        inc brickhitx
        add esi,edx
        mov dl,byte ptr [esi]
        jmp CheckBallCollision_exit
    downright:
        mov esi,current_level_screen
        movzx edx,bally
        inc edx
        inc brickhity
        imul edx,121
        add esi,edx
        movzx edx,ballx
        inc edx
        inc brickhitx
        add esi,edx
        mov dl,byte ptr [esi]
        jmp CheckBallCollision_exit
    downleft:
        mov esi,current_level_screen
        movzx edx,bally
        inc edx
        inc brickhity
        imul edx,121
        add esi,edx
        movzx edx,ballx
        dec edx
        dec brickhitx
        add esi,edx
        mov dl,byte ptr [esi]
        jmp CheckBallCollision_exit
    upleft:
        mov esi,current_level_screen
        movzx edx,bally
        dec edx
        dec brickhity
        imul edx,121
        add esi,edx
        movzx edx,ballx
        dec edx
        dec brickhitx
        add esi,edx
        mov dl,byte ptr [esi]
        jmp CheckBallCollision_exit

CheckBallCollision_exit:

    mov cl,brickhitx
    mov ch,brickhity

    cmp yPos,ch
    jne nopaddle
    cmp xPos,cl
    ja nopaddle
    sub cl,paddlelength
    inc cl
    cmp xPos,cl
    jb nopaddle

    mov dl,'|'

    nopaddle:

ret
CheckBallCollision ENDP

BrickHit PROC
    mov dl,byte ptr [esi]
    dec dl
    cmp dl,'a'
    jae nosp1
    mov dl,' '
    nosp1:
    mov [esi],dl
    
    mov edi,esi
    call BrickUpdate

    mov bl,brickhitx
    mov edi,esi
    dec edi
    dec brickhitx
    leftbrickcheck:
        mov dl,byte ptr [edi]
        cmp dl,' '
        je leftbrickcheck_exit

        dec dl
        cmp dl,'a'
        jae nosp2
        mov dl,' '
        nosp2:
        mov [edi],dl
        call BrickUpdate
        dec edi
        dec brickhitx
        jmp leftbrickcheck

    leftbrickcheck_exit:

    mov brickhitx,bl
    mov edi,esi
    inc edi
    inc brickhitx
    rightbrickcheck:
        mov dl,byte ptr [edi]
        cmp dl,' '
        je rightbrickcheck_exit

        dec dl
        cmp dl,'a'
        jae nosp3
        mov dl,' '
        nosp3:
        mov [edi],dl
        call BrickUpdate
        inc edi
        inc brickhitx
        jmp rightbrickcheck

    rightbrickcheck_exit:


ret
BrickHit ENDP

BrickUpdate PROC

    dec brickcount

    cmp dl,' '
    je space_found
    cmp dl,'a'
    je first_found
    cmp dl,'b'
    je sec_found
    cmp dl,'c'
    je spec_found
    cmp dl,'d'
    je bomb_found

    space_found:
        add score,5
        mov eax,black
        call settextcolor
        mov al,dl
        jmp BrickUpdate_exit
    first_found:
        add score,10
        mov eax,brick1color
        call settextcolor
        mov al,dl
        jmp BrickUpdate_exit
    sec_found:
        add score,15
        mov eax,brick2color
        call settextcolor
        mov al,dl
        jmp BrickUpdate_exit
    spec_found:
        call SpawnPowerUp
        add score,5
        mov eax,black
        call settextcolor
        mov al,' '
        mov [edi],al
        jmp BrickUpdate_exit
    bomb_found:
        add score,20
        mov eax,black
        call settextcolor
        call BombExplosion
        mov al,' '
        mov [edi],al
        jmp BrickUpdate_exit

    BrickUpdate_exit:
        mov dl,brickhitx
        mov dh,brickhity
        call GoToXY
        call WriteChar

ret
BrickUpdate ENDP

SpawnPowerUp PROC

    cmp PowerUpSpawned,1
    je SpawnPowerUp_exit

    mov PowerUpSpawned,1

    mov eax,1
    call RandomRange

    cmp al,0
    je specball
    cmp al,1 
    je multiball

    specball:
       mov PowerUpType,'s' 
       jmp powerupdecided
    multiball:
       mov PowerUpType,'m'
       jmp powerupdecided

    powerupdecided:
        mov dl,PowerUpx
        mov dh,PowerUpy
        call GoToXY
        mov al,PowerUpType
        call WriteChar

SpawnPowerUp_exit:
ret
SpawnPowerUp ENDP

BombExplosion PROC

    mov al,brickhitx
    push eax
    mov al,brickhity
    push eax
    push edi
    push esi

    cmp explodedbool,1
    je BombExplosion_exit

    mov explodednum,0
    mov randomx,0
    mov randomy,0
    exploder:
        mov eax,73
        call RandomRange
        add eax,23
        mov randomx,al
        
        mov eax,7
        call RandomRange
        add eax,4
        mov randomy,al

        mov esi,current_level_screen
        movzx edx,randomy
        imul edx,121
        add esi,edx
        movzx edx,randomx
        add esi,edx
        mov dl,byte ptr [esi]

        cmp dl,'a'
        jb exploder
        cmp dl,'c'
        ja exploder

        mov al,randomx
        mov brickhitx,al
        mov al,randomy
        mov brickhity,al
        call BrickHit
        inc explodednum

        mov eax,300
        call delay

        cmp explodednum,5
        jb exploder

mov explodedbool,1
mov eax,500
call Delay

BombExplosion_exit:
pop esi
pop edi
pop eax
mov brickhity,al
pop eax
mov brickhitx,al
ret
BombExplosion ENDP

headingPrint PROC
;border
    mov eax,magenta + (magenta * 16)
    call SetTextColor
    mov dl,0
    mov dh,29
    call Gotoxy
    mov edx,OFFSET border
    call WriteString
    mov dl,0
    mov dh,0
    call Gotoxy
    mov edx,OFFSET border
    call WriteString

    mov ecx,29
    mov dh,0
    mov newT, dh
    l22:
    mov dh, newT
    mov dl,0
    call Gotoxy
    mov edx,OFFSET border1
    call WriteString
    inc newT
    loop l22

    mov ecx,30
    mov dh,0
    mov t,dh
    l44:
    mov dh,t
    mov dl,119
    call gotoxy
    mov edx,offset border2
    call writestring
    inc t
    loop l44

    mov ecx,29
    mov dh,0
    mov T,dh
    l33:
    mov dh,T
    mov dl,118
    call Gotoxy
    mov edx,OFFSET border2
    call WriteString
    inc T
    loop l33

    mov ecx,29
    mov dh,0
    mov newT, dh
    l11:
    mov dh, newT
    mov dl,1
    call Gotoxy
    mov edx,OFFSET border1
    call WriteString
    inc newT
    loop l11



    ;printing heading
    mov xheadingPos, 10
    mov yheadingPos, 7

    mov eax, 0
    mov esi, offset heading
    mov ecx, 8
    headingxDisplay:
        mov eax,300
        call Delay
        push ecx
        mov ecx, 99
        headingyDisplay:
        mov al, [esi]
        mov dl, xheadingPos
        mov dh, yheadingPos
        call Gotoxy

        cmp al, " "
        je Spaceitis

        mov eax,yellow + (black * 16)
        call SetTextColor
        mov al, [esi]
        call WriteChar



        Spaceitis:

        inc xheadingPos
        cmp xheadingPos, 109
        jne noReset
        mov xheadingPos, 10
        inc yheadingPos

        noReset:
        inc esi     

        loop headingyDisplay

        pop ecx
    loop headingxDisplay


    menudisplay:

        mov eax,white (black * 16)
        call SetTextColor

        mov dl,93
        mov dh,21
        call Gotoxy
        mov edx,OFFSET StartString
        call WriteString


        mov dl,93
        mov dh,23
        call Gotoxy
        mov edx,OFFSET OptionString
        call WriteString

        mov dl,93
        mov dh,25
        call Gotoxy
        mov edx,OFFSET ExitString
        call WriteString

        
        mov eax,0

    headingLoop: 


        call ReadChar

        mov inputChar,al

        cmp inputChar, "i"
        je optionslabel

        cmp inputChar, 13
        je enterName


    jmp headingLoop

    optionslabel:
        call DrawOptions
    optionslooper:

        call ReadChar

        mov inputChar,al

        cmp inputChar,'m'
        je mute

        cmp inputChar,'c'
        je enablecheat

        cmp inputChar,'x'
        je menudisplay

        jmp optionslooper

        mute:
            mov eax, SND_FILENAME  
            or eax, SND_LOOP       
            or eax, SND_ASYNC 
            invoke PlaySound, NULL,0,eax
            jmp optionslooper
        enablecheat:
            mov cheatbool,1 
            jmp optionslooper
        

    enterName:
    call enterNamePrint

    exitheadingPrinting:

ret
headingPrint ENDP

enterNamePrint PROC

        mov eax,black + (black * 16)
        call SetTextColor


        mov edx,0
        mov dl,30
        mov dh,18

        mov ecx, 25
        
        EraseLine:

            call Gotoxy
            mov al, " "
            call WriteChar

            inc dl

        loop EraseLine

        mov edx,0
        mov dl,28
        mov dh,20

        mov ecx, 25
        EraseLine1:

            call Gotoxy
            mov al, " "
            call WriteChar

            inc dl

        loop EraseLine1


         ;////////////Enter Name Printing////////////////

         ;////////Red border around enter name////////////

        mov eax,red + (black * 16)
        call SetTextColor
        
        mov dl,30
        mov dh,16
        call Gotoxy
        mov edx,OFFSET border3
        call WriteString

        mov dl,30
        mov dh,18
        call Gotoxy
        mov edx,OFFSET border3
        call WriteString

        mov dl,29
        mov dh,17
        call Gotoxy
        mov edx,OFFSET border1
        call WriteString

        mov dl,58
        mov dh,17
        call Gotoxy
        mov edx,OFFSET border1
        call WriteString

        ;////////End red border around enter name////////////


        mov eax,white (black * 16)
        call SetTextColor

        mov dl,32
        mov dh,17
        call Gotoxy
        mov edx,OFFSET InputNameString
        call WriteString

        mov edx,0
        mov  edx, offset player_name
        mov  ecx, 15        
        call ReadString

        mov ecx,10
        mov ebp,0
        standardizer_loop:
            cmp player_name[ebp],0Ah
            jne standardizer_loop_cont

            mov player_name[ebp],0

            standardizer_loop_cont:
            inc ebp
            LOOP standardizer_loop

        mov dl,57
        add dl, al
        mov nameSize, al

        mov dh,17
        call Gotoxy
        ret

enterNamePrint ENDP

DrawOptions PROC

        mov eax,white (black * 16)
        call SetTextColor

        mov dl,93
        mov dh,21
        call Gotoxy
        mov edx,OFFSET MuteString
        call WriteString


        mov dl,93
        mov dh,23
        call Gotoxy
        mov edx,OFFSET CheatString
        call WriteString

        mov dl,93
        mov dh,25
        call Gotoxy
        mov edx,OFFSET ExitString
        call WriteString

ret
DrawOptions ENDP

InitializeLevel PROC
        call getMseconds
        mov lastmove,eax
        mov lastmove2,eax

        cmp currentlevel,1
        je go_to_level_1
        cmp currentlevel,2
        je go_to_level_2
        cmp currentlevel,3
        je go_to_level_3
        
        call GameOver

        go_to_level_1:
            mov current_level_screen,OFFSET game_screen1
            mov PowerUpx,89
            mov PowerUpy,10
            mov brickcount,172
            jmp InitializeLevel_exit
        go_to_level_2:
            mov paddle[3],0
            mov paddle_x[3],0
            mov paddlelength,3
            mov current_level_screen,OFFSET game_screen2
            mov brickcount,124
            mov PowerUpx,38
            mov PowerUpy,10
            mov ballx,60
            mov bally,23
            mov secondballx,60
            mov secondbally,23
            mov explodedbool,0
            mov poweredupbool,0
            mov secondballbool,0
            mov ballspeed,400
            jmp InitializeLevel_exit
        go_to_level_3:
            mov current_level_screen,OFFSET game_screen3
            mov brickcount,188
            mov ballx,60
            mov bally,23
            mov secondballx,60
            mov secondbally,23
            mov explodedbool,0
            mov poweredupbool,0
            mov secondballbool,0
            mov ballspeed,300
            jmp InitializeLevel_exit

InitializeLevel_exit:
ret
InitializeLevel ENDP

GameOver PROC


        call WriteHighScoreFile

        call clrscr
        mov eax,lightred
        call settextcolor
        mov edx,offset ending_screen
        call writestring

        mov dl,60
        mov dh,18
        call gotoxy
        mov edx,offset player_name
        call writestring
    
        mov dl,75
        mov dh,18
        call gotoxy
        mov eax,score
        call writeint

        mov eax,5000
        call delay

        exit

ret
GameOver ENDP

DrawBall2 PROC
    mov eax,lightmagenta
    call SetTextColor
    mov dl,secondballx
    mov dh,secondbally
    call Gotoxy
    mov al,'0'
    call WriteChar
    ret
DrawBall2 ENDP

UpdateBall2 PROC
    mov eax,black
    call SetTextColor
    mov dl,secondballx
    mov dh,secondbally
    call Gotoxy
    mov al,' '
    call WriteChar
    ret
UpdateBall2 ENDP

MoveBall2 PROC

    cmp secondballbool,1
    jne MoveBall2_exit

    call getMseconds
    mov ebx,eax
    sub eax,lastmove2

    cmp eax,ballspeed
    jae MoveBall2_start

    ret

    MoveBall2_start:

        cmp secondbally,26
        jne nodeath2
        
        ; death 

        call UpdateBall2
        mov secondballbool,0
        jmp MoveBall2_exit

        nodeath2:
        mov lastmove2,ebx
        call CheckBall2Collision

        check_collison2:
            cmp dl,' '
            je nocollision2
            cmp dl,'|'
            je change_dir2

            call BrickHit

            change_dir2:
                call ChangeDirection2

            nocollision2:
                cmp secondballdir,1
                je upright_m2
                cmp secondballdir,2
                je downright_m2
                cmp secondballdir,3
                je downleft_m2
                cmp secondballdir,4
                je upleft_m2

            
                upright_m2:
                    call UpdateBall2
                    inc secondballx
                    dec secondbally
                    call DrawBall2
                    jmp MoveBall2_exit
                downright_m2:
                    call UpdateBall2
                    inc secondballx
                    inc secondbally
                    call DrawBall2
                    jmp MoveBall2_exit
                downleft_m2:
                    call UpdateBall2
                    dec secondballx
                    inc secondbally
                    call DrawBall2
                    jmp MoveBall2_exit
                upleft_m2:
                    call UpdateBall2
                    dec secondballx
                    dec secondbally
                    call DrawBall2
                    jmp MoveBall2_exit
            

MoveBall2_exit:
ret
MoveBall2 ENDP

ChangeDirection2 PROC
pushad

    sub esi,121
    mov dl,byte ptr [esi]

    cmp secondbally,1
    je upperhit2

    cmp dl,' '
    je brickshit2

    wallhit2:
        cmp secondballdir,1
        je upright_ch2
        cmp secondballdir,2
        je downright_ch2
        cmp secondballdir,3
        je downleft_ch2
        cmp secondballdir,4
        je upleft_ch2

        upright_ch2:
            mov secondballdir,4
            jmp ChangeDirection2_exit
        downright_ch2:
            mov secondballdir,3
            jmp ChangeDirection2_exit
        downleft_ch2:
            mov secondballdir,2
            jmp ChangeDirection2_exit
        upleft_ch2:
            mov secondballdir,1
            jmp ChangeDirection2_exit 

    brickshit2:
        cmp secondballdir,1
        je upright_cha2
        cmp secondballdir,2
        je downright_cha2
        cmp secondballdir,3
        je downleft_cha2
        cmp secondballdir,4
        je upleft_cha2

        upright_cha2:
            mov secondballdir,2
            jmp ChangeDirection2_exit
        downright_cha2:
            mov secondballdir,1
            jmp ChangeDirection2_exit
        downleft_cha2:
            mov secondballdir,4
            jmp ChangeDirection2_exit
        upleft_cha2:
            mov secondballdir,3
            jmp ChangeDirection2_exit 

    upperhit2:
        cmp secondballdir,1
        je upright_chau2
        cmp secondballdir,4
        je upleft_chau2

        upright_chau2:
            mov secondballdir,2
            jmp ChangeDirection2_exit
        upleft_chau2:
            mov secondballdir,3
            jmp ChangeDirection2_exit 
        
   

ChangeDirection2_exit:
popad
ret
ChangeDirection2 ENDP

CheckBall2Collision PROC

    mov dl,secondballx
    mov brickhitx,dl
    mov dl,secondbally
    mov brickhity,dl
    
    cmp secondballdir,1
    je upright2
    cmp secondballdir,2
    je downright2
    cmp secondballdir,3
    je downleft2
    cmp secondballdir,4
    je upleft2

    upright2:
        mov esi,current_level_screen
        movzx edx,secondbally
        dec edx
        dec brickhity
        imul edx,121
        add esi,edx
        movzx edx,secondballx
        inc edx
        inc brickhitx
        add esi,edx
        mov dl,byte ptr [esi]
        jmp CheckBall2Collision_exit
    downright2:
        mov esi,current_level_screen
        movzx edx,secondbally
        inc edx
        inc brickhity
        imul edx,121
        add esi,edx
        movzx edx,secondballx
        inc edx
        inc brickhitx
        add esi,edx
        mov dl,byte ptr [esi]
        jmp CheckBall2Collision_exit
    downleft2:
        mov esi,current_level_screen
        movzx edx,secondbally
        inc edx
        inc brickhity
        imul edx,121
        add esi,edx
        movzx edx,secondballx
        dec edx
        dec brickhitx
        add esi,edx
        mov dl,byte ptr [esi]
        jmp CheckBall2Collision_exit
    upleft2:
        mov esi,current_level_screen
        movzx edx,secondbally
        dec edx
        dec brickhity
        imul edx,121
        add esi,edx
        movzx edx,secondballx
        dec edx
        dec brickhitx
        add esi,edx
        mov dl,byte ptr [esi]
        jmp CheckBall2Collision_exit

CheckBall2Collision_exit:

    mov cl,brickhitx
    mov ch,brickhity

    cmp yPos,ch
    jne nopaddle2
    cmp xPos,cl
    ja nopaddle2
    sub cl,paddlelength
    inc cl
    cmp xPos,cl
    jb nopaddle2

    mov dl,'|'

    nopaddle2:

ret
CheckBall2Collision ENDP

; ///////////////////// FILE HANDLING /////////////////////////

stats_array_maker PROC

        mov al, [esi]
        mov top5_stats_str[0], al
        mov al, [esi + 1]
        mov top5_stats_str[1], al
        mov al, [esi + 2]
        mov top5_stats_str[2], al
        mov al, [esi + 3]
        mov top5_stats_str[3], al
        mov al, [esi + 4]
        mov top5_stats_str[4], al
        mov al, [esi + 5]
        mov top5_stats_str[5], al
        mov al, [esi + 6]
        mov top5_stats_str[6], al
        mov al, [esi + 7]
        mov top5_stats_str[7], al
        mov al, [esi + 8]
        mov top5_stats_str[8], al
        mov al, [esi + 9]
        mov top5_stats_str[9], al
        mov al, ' '
        mov top5_stats_str[10], al
        mov al, [esi + 10]
        mov top5_stats_str[11], al
        mov al, [esi + 11]
        mov top5_stats_str[12], al
        mov al, [esi + 12]
        mov top5_stats_str[13], al
        mov al, [esi + 13]
        mov top5_stats_str[14], al
        mov al, ' '
        mov top5_stats_str[15], al
        mov al, [esi+14]
        mov top5_stats_str[16], al

        mov ecx,15
        mov ebp,0
    spacer_loop:
        cmp top5_stats_str[ebp],0
        jne spacer_loop_cont

        mov top5_stats_str[ebp],' '

        spacer_loop_cont:
        inc ebp
        LOOP spacer_loop

        mov top5_stats_str[17],0

ret
stats_array_maker ENDP

MakeHighScoreFile PROC

    mov ebx,GENERIC_READ
    OR ebx,GENERIC_WRITE
    invoke CreateFile ,offset highscores_file_name,ebx,0,NULL,OPEN_ALWAYS,FILE_ATTRIBUTE_NORMAL,highscores_file_handle
    mov highscores_file_handle,eax
    mov eax,highscores_file_handle
    call closefile

    mov edx,OFFSET highscores_file_name
    call OpenInputFile
    mov highscores_file_handle,eax

    call WriteWindowsMsg
ret
MakeHighScoreFile ENDP

ReadHighScoreFile PROC

    mov  eax,highscores_file_handle
    mov  edx,offset filehandling_array
    mov  ecx,lengthof filehandling_array
    call readfromfile

    mov eax,highscores_file_handle
    call closefile

ret
ReadHighScoreFile ENDP

WriteHighScoreFile PROC

      mov  edx,OFFSET highscores_file_name
      call CreateOutputFile
      mov  highscores_file_handle,eax

    mov esi,offset filehandling_array
    mov ecx,10
    mov temp_index,0
    placer_loop:
        mov dl,'-'
        cmp [esi],dl
        je place_here

        mov temp_filehandling_score,0
        movzx eax,byte ptr[esi+10]
        sub eax,48
        imul eax,1000
        add temp_filehandling_score,eax
        movzx eax,byte ptr[esi+11]
        sub eax,48
        imul eax,100
        add temp_filehandling_score,eax
        movzx eax,byte ptr[esi+12]
        sub eax,48
        imul eax,10
        add temp_filehandling_score,eax
        movzx eax,byte ptr[esi+13]
        sub eax,48
        add temp_filehandling_score,eax

        mov eax,score
        cmp temp_filehandling_score,eax
        jbe place_here

        add esi,15
        inc temp_index
    LOOP placer_loop

    
    mov eax,highscores_file_handle
    call closefile
    ret


    place_here:
        mov al,[esi]
        mov temp_filehandling_array2[0],al
        mov al,[esi+1]
        mov temp_filehandling_array2[1],al
        mov al,[esi+2]
        mov temp_filehandling_array2[2],al
        mov al,[esi+3]
        mov temp_filehandling_array2[3],al
        mov al,[esi+4]
        mov temp_filehandling_array2[4],al
        mov al,[esi+5]
        mov temp_filehandling_array2[5],al
        mov al,[esi+6]
        mov temp_filehandling_array2[6],al
        mov al,[esi+7]
        mov temp_filehandling_array2[7],al
        mov al,[esi+8]
        mov temp_filehandling_array2[8],al
        mov al,[esi+9]
        mov temp_filehandling_array2[9],al
        mov al,[esi+10]
        mov temp_filehandling_array2[10],al
        mov al,[esi+11]
        mov temp_filehandling_array2[11],al
        mov al,[esi+12]
        mov temp_filehandling_array2[12],al
        mov al,[esi+13]
        mov temp_filehandling_array2[13],al
        mov al,[esi+14]
        mov temp_filehandling_array2[14],al


        mov al,player_name[0]
        mov byte ptr [esi],al
        mov al,player_name[1]
        mov byte ptr [esi+1],al
        mov al,player_name[2]
        mov byte ptr [esi+2],al
        mov al,player_name[3]
        mov byte ptr [esi+3],al
        mov al,player_name[4]
        mov byte ptr [esi+4],al
        mov al,player_name[5]
        mov byte ptr [esi+5],al
        mov al,player_name[6]
        mov byte ptr [esi+6],al
        mov al,player_name[7]
        mov byte ptr [esi+7],al
        mov al,player_name[8]
        mov byte ptr [esi+8],al
        mov al,player_name[9]
        mov byte ptr [esi+9],al
        mov eax,score
        mov cl,'0'
        mov edx,0
        mov ebx,0
        mov bl,10
        div ebx
        add cl,dl
        mov byte ptr [esi+13],cl
        mov cl,'0'
        mov edx,0
        mov ebx,0
        mov bl,10
        div ebx
        add cl,dl
        mov byte ptr [esi+12],cl
        mov cl,'0'
        mov edx,0
        mov ebx,0
        mov bl,10
        div ebx
        add cl,dl
        mov byte ptr [esi+11],cl
        mov cl,'0'
        add cl,al
        mov byte ptr [esi+10],cl
        mov cl,'0'
        add cl,currentlevel
        mov byte ptr [esi+14],cl

        add esi,15

        mov ecx,10
        sub ecx,temp_index
        dec ecx
        swapper_loop:
            mov al,[esi]
            mov temp_filehandling_array[0],al
            mov al,[esi+1]
            mov temp_filehandling_array[1],al
            mov al,[esi+2]
            mov temp_filehandling_array[2],al
            mov al,[esi+3]
            mov temp_filehandling_array[3],al
            mov al,[esi+4]
            mov temp_filehandling_array[4],al
            mov al,[esi+5]
            mov temp_filehandling_array[5],al
            mov al,[esi+6]
            mov temp_filehandling_array[6],al
            mov al,[esi+7]
            mov temp_filehandling_array[7],al
            mov al,[esi+8]
            mov temp_filehandling_array[8],al
            mov al,[esi+9]
            mov temp_filehandling_array[9],al
            mov al,[esi+10]
            mov temp_filehandling_array[10],al
            mov al,[esi+11]
            mov temp_filehandling_array[11],al
            mov al,[esi+12]
            mov temp_filehandling_array[12],al
            mov al,[esi+13]
            mov temp_filehandling_array[13],al
            mov al,[esi+14]
            mov temp_filehandling_array[14],al
            
            mov al, temp_filehandling_array2[0]
            mov [esi], al
            mov al, temp_filehandling_array2[1]
            mov [esi + 1], al
            mov al, temp_filehandling_array2[2]
            mov [esi + 2], al
            mov al, temp_filehandling_array2[3]
            mov [esi + 3], al
            mov al, temp_filehandling_array2[4]
            mov [esi + 4], al
            mov al, temp_filehandling_array2[5]
            mov [esi + 5], al
            mov al, temp_filehandling_array2[6]
            mov [esi + 6], al
            mov al, temp_filehandling_array2[7]
            mov [esi + 7], al
            mov al, temp_filehandling_array2[8]
            mov [esi + 8], al
            mov al, temp_filehandling_array2[9]
            mov [esi + 9], al
            mov al, temp_filehandling_array2[10]
            mov [esi + 10], al
            mov al, temp_filehandling_array2[11]
            mov [esi + 11], al
            mov al, temp_filehandling_array2[12]
            mov [esi + 12], al
            mov al, temp_filehandling_array2[13]
            mov [esi + 13], al
            mov al, temp_filehandling_array2[14]
            mov [esi + 14], al

            mov al, temp_filehandling_array[0]
            mov temp_filehandling_array2[0], al

            mov al, temp_filehandling_array[1]
            mov temp_filehandling_array2[1], al

            mov al, temp_filehandling_array[2]
            mov temp_filehandling_array2[2], al

            mov al, temp_filehandling_array[3]
            mov temp_filehandling_array2[3], al

            mov al, temp_filehandling_array[4]
            mov temp_filehandling_array2[4], al

            mov al, temp_filehandling_array[5]
            mov temp_filehandling_array2[5], al

            mov al, temp_filehandling_array[6]
            mov temp_filehandling_array2[6], al

            mov al, temp_filehandling_array[7]
            mov temp_filehandling_array2[7], al

            mov al, temp_filehandling_array[8]
            mov temp_filehandling_array2[8], al

            mov al, temp_filehandling_array[9]
            mov temp_filehandling_array2[9], al

            mov al, temp_filehandling_array[10]
            mov temp_filehandling_array2[10], al

            mov al, temp_filehandling_array[11]
            mov temp_filehandling_array2[11], al

            mov al, temp_filehandling_array[12]
            mov temp_filehandling_array2[12], al

            mov al, temp_filehandling_array[13]
            mov temp_filehandling_array2[13], al

            mov al, temp_filehandling_array[14]
            mov temp_filehandling_array2[14], al

            add esi,15
        dec ecx
        cmp ecx,0
        jne swapper_loop
        

    mov  eax,highscores_file_handle
    mov  edx,offset filehandling_array
    mov  ecx,lengthof filehandling_array
    call writetoFile

    mov eax,highscores_file_handle
    call closefile

ret
WriteHighScoreFile ENDP


END
