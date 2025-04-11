def caesar(text, shift):
    # تشفير النص باستخدام إزاحة معينة.
    r = ""
    for char in text:
        if char.isalpha():
            # تحديد ما إذا كان الحرف كبيرًا أم صغيرًا
            if char.isupper():
                x = ord('A')
            else:
                x = ord('a')
            # تشفير الحرف
            r += chr((ord(char) - x + shift) % 26 + x)
        else:
            # إذا كان الحرف ليس حرفًا أبجديًا، نضيفه كما هو
            r += char
    return r

def all_shifting(text):
    # حساب جميع احتمالات التشفير (25 مرة).
    for shift in range(1,26):  # نبدأ من 1 إلى 25
        encrypted_text = caesar(text, shift)
        print(f"{shift}: {encrypted_text}")

all_shifting("waleed")
