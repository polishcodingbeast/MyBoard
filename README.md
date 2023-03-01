# Hangman
def recognize_word(word):
    word = word.lower()
    table_of_letters = list(word)
    empty_tab = ['_']*len(word)
    lives = len(word)
    print('Hello in title game "Hangman".')
    print('You have to write letters and guess the word!')

    while lives > 0 and empty_tab != table_of_letters:
        letter = input('Write a letter: ').lower()

        if letter in table_of_letters:
            print('You guessed!')
            for i, char in enumerate(word):
                if char == letter:
                    empty_tab[i] = letter
            print(empty_tab)
        else:
            lives -= 1
            print('This letter is not in the word, you have', lives, 'lives left.')

    if empty_tab == table_of_letters:
        print('Congratulations, you won!')
    else:
        print('You lost. The word was:', word)


word = 'dasdwadwa'

recognize_word(word)
