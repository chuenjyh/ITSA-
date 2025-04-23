# ITSA-# 定義每個數字的矩陣表示
DIGIT_MATRIX = {
    '0': [" *** ", "*   *", "*   *", "*   *", " *** "],
    '1': ["  *  ", " **  ", "  *  ", "  *  ", " *** "],
    '2': [" *** ", "    *", " *** ", "*    ", " *** "],
    '3': [" *** ", "    *", " *** ", "    *", " *** "],
    '4': ["*   *", "*   *", " *** ", "    *", "    *"],
    '5': [" *** ", "*    ", " *** ", "    *", " *** "],
    '6': [" *** ", "*    ", " *** ", "*   *", " *** "],
    '7': [" *** ", "    *", "    *", "    *", "    *"],
    '8': [" *** ", "*   *", " *** ", "*   *", " *** "],
    '9': [" *** ", "*   *", " *** ", "    *", " *** "],
}

def display_matrix_number(number):
    # 將輸入的數字轉為字串
    number_str = str(number).zfill(4)  # 確保是四位數，若不足補零
    if len(number_str) != 4 or not number_str.isdigit():
        print("請輸入四個整數！")
        return

    # 初始化矩陣行
    rows = [""] * 5

    # 將每個數字的矩陣行拼接
    for digit in number_str:
        digit_matrix = DIGIT_MATRIX[digit]
        for i in range(5):
            rows[i] += digit_matrix[i] + "  "

    # 輸出矩陣數字
    for row in rows:
        print(row)

if __name__ == "__main__":
    # 從使用者輸入四位數字
    user_input = input("請輸入四位數字：")
    display_matrix_number(user_input)
