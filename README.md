# DieselTXT_CSV
Intermediate between sl_decoder and translator++ for dieselmine games. Tested only on MV ones.
# Requirements
1. SL_Decoder: https://github.com/Sinflower/SL_Decoder 
2. Translator++: http://dreamsavior.net/translator-plusplus/ 
# Steps
1. Decode .sl files using SL_Decoder tool.
2. Do a copy for backup of both txt and sl files.
3. Use my tool in CMD like this: DieselTXT_CSV.exe -export "your folder with txt"
4. Result is in your input folder, in a folder called csv.
5. Create new project in Translator++ as Spreadsheet. Select the csv folder and use default options.
6. Translate the text you want. Be aware to use only the Initial column for translation. This don't support multiple translations on import process. Also don't add line breaks to any text, since the game has a auto line break system for text display.
7. After you do the changes, do right-click on the files you want to export, then select X selected > Export into... > RMTrans Patch. Select your export folder.
8. Use my tool in CMD to import the new translated .csv onto .txt like: DieselTXT_CSV.exe -import "your folder with new csv" "your folder with txt". Be aware to <b>NEVER</b> change names of both files, since my tool use it to search on what files text need to be replaced.
9. Finally, use SL_Decoder to encode to .sl again.
10. Test changes on the game.
# Fix line break limit on game
Be aware this example is for "In a certain mansion..." game. Other games maybe change where to edit these lines.
1. Go to \www\js\plugins\ and open TS_ADVsystem.js
2. Search line this.ESCAPE and replace the value with: /^[\$\.\|\^!><\{\}\[\]\\]|^[A-Z]|^[a-z]|^\d/;
3. Search line this.NO_SPACE and replace the value with: /\69/i;
4. Search line this.VIEW_TEXT_NUM and replace the value with a higher number. For this game, 60 do the work.
5. If you want to have less margin on left side of the text, go to this.SPACE_AJASUTO and change this with: " ";
6. Save the file, then test with the game.
