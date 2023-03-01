#tic tac toe
def game(tab1, tab2, tab3):
    columns = [tab1, tab2, tab3]
    x = 0
    while x < 9:
        x += 1
        place_column = int(
            input('choose which column you want to put your character: '))
        place_row = int(
            input('choose which row you want to put your character: '))
        if place_column not in [1, 2, 3] or place_row not in [1, 2, 3]:
            x -= 1
            print(x)
            continue
        column = columns[place_column - 1]
        if column[place_row - 1] == '.':
            column[place_row - 1] = which_player(x)
            show_board()
            winner = who_is_the_winner(columns)
            if winner:
                print(winner)
                break
        else:
            x -= 1
            print(x)
            continue


def which_player(x):
    return 'x' if x % 2 == 0 else 'o'


def who_is_the_winner(columns):
    wins = [('o',)*3, ('x',)*3]
    rows = [[columns[c][r] for c in range(3)] for r in range(3)]
    diags = [[columns[i][i] for i in range(3)],
             [columns[2-i][i] for i in range(3)]]
    for row in rows + diags:
        if tuple(row) in wins:
            return f"won {row[0]}"
    for column in columns:
        if tuple(column) in wins:
            return f"won {column[0]}"
    return None


def show_board():
    print(tab1)
    print(tab2)
    print(tab3)


tab1 = ['.', '.', '.']
tab2 = ['.', '.', '.']
tab3 = ['.', '.', '.']
game(tab1, tab2, tab3)
