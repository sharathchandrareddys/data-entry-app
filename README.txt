
INSTRUCTIONS TO GENERATE .EXE

1. Make sure Python and pip are installed.
2. Install pyinstaller if not already installed:
   pip install pyinstaller

3. Open CMD and navigate to this folder:
   cd [extracted folder path]

4. Run this command to generate exe:
   pyinstaller --onefile --windowed --icon=icon.ico data_entry_app.py

5. After successful run, go to /dist/ and find your .exe file

NOTE:
- Replace the current icon.ico with your actual .ico file
- Replace the placeholder script with your final Python app code
