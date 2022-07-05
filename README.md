# imessages-bot
NOTES : Script hanya berfungsi pada Mac karena menggunakan AppleScript.

Pada file send.scpt terdapat applescript yang akan mengirim pesan melalui iMessage:

on run {targetPhoneNumber, targetMessageToSend}
    tell application "Messages"
        set targetService to 1st service whose service type = iMessage
        set targetBuddy to buddy targetPhoneNumber of targetService
        set targetMessage to targetMessageToSend
        send targetMessage to targetBuddy
    end tell
end run

Lalu, command akan dipanggil melalui file main.py 
os.system('osascript send.scpt {} "{}"'.format(phone_number, message))

Yang artinya memberitahu Mac untuk menjalankan applescript yang definisikan dengan nomor telepon dan pesan yang txt yang telah diberikan. 
Jadi kita dapat mengirim satu kata pada satu waktu jika hanya membuat for loop dan menjalankan baris ini berkali-kali, 
di mana pesannya setiap kali adalah satu kata tersebut.
