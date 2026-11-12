
def print_board(board, n):
    for i in range(n):
        for j in range(n):
            print(board[i][j], end=" ")
        print()


def is_safe(board, row, col, n):

    # Check column
    for i in range(row):
        if board[i][col] == 1:
            return False

    # Check upper-left diagonal
    i, j = row - 1, col - 1

    while i >= 0 and j >= 0:
        if board[i][j] == 1:
            return False
        i -= 1
        j -= 1

    # Check upper-right diagonal
    i, j = row - 1, col + 1

    while i >= 0 and j < n:
        if board[i][j] == 1:
            return False
        i -= 1
        j += 1

    return True


def solve(board, row, n):

    if row == n:
        return True

    for col in range(n):
        if is_safe(board, row, col, n):

            board[row][col] = 1

            if solve(board, row + 1, n):
                return True

            board[row][col] = 0

    return False


n = int(input("Enter N: "))

board = [[0 for j in range(n)] for i in range(n)]

first_col = int(input("Enter first Queen column (0 to n-1): "))

# Place first Queen in row 0
if 0 <= first_col < n:
    board[0][first_col] = 1

    if solve(board, 1, n):
        print("\nN-Queens Solution:")
        print_board(board, n)
    else:
        print("No solution exists for this position.")
else:
    print("Invalid column!")
