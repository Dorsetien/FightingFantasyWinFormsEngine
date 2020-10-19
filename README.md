# FightingFantasyWinFormsEngine
Fighting Fantasy Engine, you just need to add your pictures, sounds and text files.  Create your own story.

Please feel free to contribute to it's development.  Done for Windows only (C# WinForms with the .Net Framework 4.7.2).  Minimum resolution : 1024 x 768.

Download the game (Engine) and double-click on "FightingFantasyWinFormsEngine.exe" (nothing to install, unzip and you're ready to play).  

I suggest you to test it with the default files then come back here to understand the contents of the text files (*.txt)

This is a nostalgia tribute to the Fighting Fantasy books and I wanted to learn c# as well so code is certainly not optimized.  

Here we go:

Your pictures, images, photos go to the "pictures" folder.  

Your text files for paragraphs must be located in the "paragraphs" directory.  

All your sounds (.wav only) go to the "audio" folder.  

Do not rename any of those directories!

Each paragraph of your story consists of a text file with different tags.  Those tags are triggers that will make changes to your character (Hero), background pictures, choices for your next paragraphs, fight with an enemy, change the amount of your gold, skill, stamina, luck points and so on.  You can even deal with equipment (max 2 equipment tags per paragraph).  Just like in the Fighting Fantasy books, you can test your luck using the right tag.  Each paragraph must contains names from 000.txt to 999.txt (so that gives you a possibility of 1000 paragraphs).  Inside each text file (.txt) you'll use the following tags to affect your story (my comments are between parentheses):

/**************************************/

<text_start>
(Everything between the text_start and text_end tags will be displayed in text section on the right of the software. This is your story there).<br>
<text_end><br>

<paragraph_choices_start><br>
001;002;003;004;005<br>
(these will display your choices of paragraph for the 5 radio button.  You can have from 1 to 5 destinations.  In this example, the choices of your .txt file being read will be 001, 002, 003, 004 or 005)<br>
<paragraph_choices_end><br>

<hero_picture_start><br>
pictures\\\hero.png<br>
(This will change the picture in the Hero picturebox. The software will read the subdirectory "pictures" then the file 000-hero.png in this example)<br>
<hero_picture_end><br>

<enemy_picture_start><br>
pictures\\\daemon.jpg<br>
(This will read the file daemon.jpg that is under the "pictures" directory.  Change will occur in the "Encounter, Illustrations, Enemy" picturebox).<br>
<enemy_picture_end><br>

<background_picture_start><br>
pictures\\\background.png<br>
(this is the background of the entire application.  Here it will read the file background.png in the "pictures" directory).<br>
<background_picture_end><br>

<enemy_points_start><br>
8;7<br>
(2 numbers to put here separated by a semicolon.  First one is the enemy skill, then the second is the enemy stamina.  This tag will trigger a fight automatically).<br>
<enemy_points_end><br>

<gold_start><br>
-8<br>
(must contain an integer.  if the number is 7, then you'll automatically gain 7 gold.  If -8, like in this example, then you'll lose 8 pieces of gold).<br>
<gold_end><br>

<equipment_start><br>
Arrow;1;-2;0 <br>
(A name, followed by a semicolon, followed by 3 integers (everything separated by a semicolon)).  (means : Name of the equipment ; influence on hero's skill ; influence on hero's stamina ; influence on hero's luck. In this example, this will add an equipment in the "equipment list" section called Arrow and the hero's skill will be incremented by 1, his stamina decreased by 2 and will have no effect on his luck).<br>
<equipment_end><br>

<equipment2_start><br>
Shield;0;2;1<br>
(I wanted the software to be able to deal with 2 items in the same paragraph so he is the tage equipment2)<br>
<equipment2_end><br>

<test_your_luck_start><br>
1<br>
(if, in a paragraph, you need the hero to test his luck, put only a 1 between those tags. IMPORTANT HERE : when you test your luck, only two paragraphs are available : Lucky : the second radiobutton is hidden, Unlucky : the first radiobutton is hidden. So, first choice lucky, 2nd option unlucky)<br>
<test_your_luck_end><br>

<skill_start><br>
3<br>
(if you need to modify the skill of your hero during a paragraph.  Here the hero will gain +3 for his skill. If you need to reset the points of skill to it's initial value, put 9999.  If you want your hero to die just put a damage of -1000 to his stamina)<br>
<skill_end><br>

<stamina_start><br>
-4<br>
(If you need to influence the stamina of your hero.  Here he will lose 4 stamina points. If you need to reset the points of stamina to it's initial value, put 9999)<br>
<stamina_end><br>

<luck_points_start><br>
1<br>
(If you need to influence the hero's luck points.  Here he will gain 1 luck point.  If you need to reset the points of luck to it's initial value, put 9999)<br>
<luck_points_end><br>

<audio_start><br>
audio\\\test.wav<br>
(this tag will trigger a sound to be played.  Here it will play the file test.wav from the directory "audio")<br>
<audio_end><br>

<ending_start><br>
1<br>
(This will trigger a messagebox saying "Victory!", this is your final paragraph where the hero wins.  Put a 1 here only.  When reaching the end (winning), gives only the option to return to paragraph 000, this will reinitialize the game)<br>
<ending_end><br>

/**************************************/

Bugs, questions, constructive comments, suggestions : dorsetienprog@gmail.com
