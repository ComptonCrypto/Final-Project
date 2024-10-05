# Final-Project
Rock, Paper, Scissors, Who??

"""The pseudocode below represents the rought draft of my game. A simple Rock, Paper, Scissors."""

BEGIN RockPaperScissorsApp

    INITIALIZE application window
    SET window title to "Rock Paper Scissors"
    
    DEFINE user_choice as None
    DEFINE options as ["Rock", "Paper", "Scissors"]

    FUNCTION SetupButtons()
        CREATE button for "Rock"
        SET button command to play_rock

        CREATE button for "Paper"
        SET button command to play_paper

        CREATE button for "Scissors"
        SET button command to play_scissors

        ADD buttons to window layout
    END FUNCTION

    FUNCTION LoadImages()
        TRY
            LOAD image "rock.png" into rock_image
            LOAD image "paper.png" into paper_image
            LOAD image "scissors.png" into scissors_image
        EXCEPTION handle error IF images are not found
    END FUNCTION

    FUNCTION SetupImageLabel()
        CREATE label for displaying images
        ADD label to window layout
    END FUNCTION

    FUNCTION play_rock()
        SET user_choice to "Rock"
        UPDATE image label to display rock_image
        CALL determine_winner()
    END FUNCTION

    FUNCTION play_paper()
        SET user_choice to "Paper"
        UPDATE image label to display paper_image
        CALL determine_winner()
    END FUNCTION

    FUNCTION play_scissors()
        SET user_choice to "Scissors"
        UPDATE image label to display scissors_image
        CALL determine_winner()
    END FUNCTION

    FUNCTION determine_winner()
        SET computer_choice to RANDOMLY select from options

        IF user_choice equals computer_choice THEN
            DISPLAY message "It's a tie!"
        ELSE IF (user_choice beats computer_choice) THEN
            DISPLAY message "You win!"
        ELSE
            DISPLAY message "You lose!"
        END IF
    END FUNCTION

    FUNCTION main()
        CALL SetupButtons()
        CALL LoadImages()
        CALL SetupImageLabel()
        
        START application main loop
    END FUNCTION

END RockPaperScissorsApp
