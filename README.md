***Python Code For Text To Audio In Android***

**Install pydroid 3**



**Website Link :** https://pydroid.app/

**Play Store Link :** https://play.google.com/store/apps/details?id=ru.iiec.pydroid3&pcampaignid=web_share

**App Store Link :** https://apps.apple.com/us/app/python3ide/id1357215444


    import tkinter as tk
    from gtts import gTTS
    import os

    def save_audio():
        text = entry.get()
        if not text:
            result_label.config(text="Please enter text.")
            return

        def on_save():
            filename = filename_entry.get()
            if not filename:
                filename_label.config(text="Enter a filename.")
                return

            
            base_path = "/storage/emulated/0/Rynapse Codes"
            os.makedirs(base_path, exist_ok=True)  

            filepath = os.path.join(base_path, f"{filename}.mp3")

            try:
                tts = gTTS(text=text, lang='en')
                tts.save(filepath)
                result_label.config(text=f"Saved to: Rynapse Codes/{filename}.mp3")
                filename_window.destroy()
            except Exception as e:
                filename_label.config(text=f"Error: {str(e)}")

        filename_window = tk.Toplevel(root)
        filename_window.title("Enter File Name")
        filename_window.geometry("300x200")

        filename_entry = tk.Entry(filename_window, font=("Arial", 12))
        filename_entry.pack(pady=10)

        filename_button = tk.Button(filename_window, text="Save", command=on_save, font=("Arial", 12))
        filename_button.pack(pady=5)

        filename_label = tk.Label(filename_window, text="", font=("Arial", 10))
        filename_label.pack(pady=5)

    root = tk.Tk()
    root.title("Text to Speech Converter")
    root.geometry("540x800")

    entry = tk.Entry(root, width=40, font=('Arial', 14))
    entry.pack(pady=20)

    convert_button = tk.Button(root, text="Convert to MP3", command=save_audio, font=('Arial', 12))
    convert_button.pack(pady=10)

    result_label = tk.Label(root, text="", font=('Arial', 12))
    result_label.pack(pady=10)

    exit_button = tk.Button(root, text="Exit", command=root.destroy, font=('Arial', 12), bg='red', fg='white')
    exit_button.place(relx=1.0, rely=1.0, anchor='se', x=-10, y=-10)

    root.mainloop()


**How to install Python Lbrary**

  1.Open CMD or Terminal 
 
  2.Run This Code
  
    pip install gTTS

**After Installing Library
Run In Python**

**How to Remove Python Library**
  
   1.Open CMD or Terminal
   
   2.Run This Code

    pip uninstall gTTS

