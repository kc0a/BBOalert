# BBOalert


Version : 2.8

The purpose of this browser extension is to reduce to the absolute minimum the manual operations due to the alerting procedure while playing bridge on BBO (www.bridgebase.com).

Main features :
- Automatic alert
- Alert recording
- Seat-dependent openings and development
- Vulnerability-dependent openings and development
- Keyboard shortcuts and abbreviations
- Full Disclosure BSS file support
- multilingual BBO user interface support

We assume that you are familiar with BBO.

## Purpose

Tired of repeating the same story while alerting your bids in BBO. If yes, this browser extension is your friend.

During the bidding, conventional calls must be alerted and explained to the opponents. Playing artificial bidding systems on BBO is not practical because explaining each alerted call is time consuming and therefore frustrating for all participants.

BBOalert solves this problem. Artificial bidding sequences can be predefined in a table. Opponents get the explanation automatically and immediately. Explanations entered manually during the game are recorded for future use.

BBOalert has similar functionality as "Full Disclosure" which is no longer supported by BBO. One difference should be emphasized :

- "Full Disclosure" served the purpose of formal and complete description of a bidding system to be maintained on BBO server. The readability of the code is extremely low due to its complexity.
- BBOalert is strictly for personal use and should help to automate the disclosure of specific agreements. The simplicity of the code makes it readable.

The program can read "Full Disclosure" old BSS files. This will enable many users of the old Windows Flash version of BBO, to migrate to the HTML version without loosing the Full Disclosure functionnality.

BBOalert is useful for all types of BBO users :

- <b>casual players without a regular partner</b> : the common bidding system for all BBO users is SAYC. In such a case, only a few bids should be alerted 'pro forma' because all players are supposed to know SAYC basics. BBOalert will record each alerted bid and will automatically recall it if an identical situation occurs. You only alert once ! The program also allows you to define keyboard shortcuts for the frequently used expressions.
- <b>'natural' players with a regular partner</b> : SAYC is simple but inefficient in many situations. Adding some gadgets gives obvious advantages. BBOalert will help to document particular agreements. By using a common database with the partner, the explanation given to the opponents will be coherent. Practicing natural systems other than SAYC imply frequent alerting because of few, but essential differences.
- <b>'artificial' players with a regular partner</b> : playing an artificial system on BBO is an impossible task. Practically every bid should be alerted and explained. Frustrated opponents will quickly abandon your table. BBOalert enables the formal description of the system in all details and provides the opponents with correct information. Advanced features enable you to differentiate seat-dependent openings and to program different defense schemes depending on the conventions used by opponents.

## Installation

### Firefox

This extension can be installed with Firefox browser using the link :

https://addons.mozilla.org/en-US/firefox/addon/bboalert

After you start BBO, the screen should look like this (note additional buttons at top/left) :

![](./images/BBOalertOK.png)

If you do not get the buttons displayed, try one of these :
- clear the Firefox cache
- remove and reinstall BBOalert
- remove and reinstall Firefox
- disable, at least temporarily, any virus protection
- disable, at least temporarily, any ad blockers
- install and try another addon from Firefox repository
- reboot the computer
- install BBOalert manually wtth Chrome

The purpose of the buttons is :

- <b>Import</b> : to read new data from the clipboard
- <b>Append</b> : to append additional data from the clipboard
- <b>Export</b> : to write manually alerted calls to the clipboard or to export data converted from BSS
- <b>Options</b> : to toggle bidding options display

You will find detailed information later in this text.

### Chrome

The extension is not published in Google's web-store.  therefore, you should install it in the CHROME browser manually from the source code :

- download BBOalert project source files in a ZIP file ("Clone or Download" button, then "Download ZIP")
- Navigate to the "Downloads" directory, open the ZIP container and expand it. This will create a subdirectory "BBOalert-master" containing project's source files.
- open Chrome browser tab with "chrome://extensions"
- make sure the Developer Mode is turned ON (in right-upper corner)
- click at "Load Unpacked" button and navigate to the "BBOalert-master" directory and confirm. BBOalert should appear on the list of the installed extensions

## How to use

The data should be stored in a CSV-formatted text file. BBOalert uses the clipboard to read this file and to export eventual updates.

BBOalert requires the following :

- BBO in split screen mode (Account + Settings + Split Screen)
- BBO used with 'Confirm Bids' enabled (Account + Settings + Confirm Bids)

At the first BBO session, you should :

- open the data file using your favorite text editor (see sections : 'Data file format'
- select all text
- copy it to the clipboard
- press "Import" button on the BBO page

All imported data is saved in browser's cache and is recalled automatically at the next session. You should use 'Import' only if the data has changed or if the cache has been cleared.

See GettingStarted.pdf for basic operations.

'Append' button allows you to add code to the previously imported code. This allows splitting data into separate files for openings and development, overcalls, and the keyboard shortcut, as examples.  

<b>Only BBOalert native code can be appended, not BSS data.</b> However, appending BBOalert native data to the previously imported BSS data is allowed.

BBOalert saves in its memory all the calls that were manually alerted during the game, With the 'Export' button you can copy this data to the clipboard and paste it into the text editor. The records imported this way will contain a timestamp and the deal number. You can retrieve from BBO the deals to review the manually alerted calls before committing the changes in your data file. <b>Manually alerted calls are not saved in the cache</b>

## Recommended way of using BBOalert

BBOalert was designed initially for BBO in English and then adapted to other languages. If you discover incompatibilies of BBOalert with BBO in your language :

- switch to https://www.bridgebase.com/v3/?lang=en
- report the problem to stanmaz.git@gmail.com

We use the "You only alert once" principle.

It is needless to code your entire system at once; it is a huge task. In each bidding system there are sequences which almost never occur.

The program records each alerted call for which no explanation has been found in the data file. Use this feature to complete your code with the bidding sequences as they come during the game. Your data file will expand as needed.

I recommend to proceed this way :

- Instead of a simple text editor, create a new file in Google Docs beginning with the keyword BBOalert
- make this file "Shareable" with write access for your partner and send him the URL link. This guarantees to be always in sync.
- enter the code for opening bids and frequently used responses
- start playing using this data (remember : select all text + copy to clipboard before starting BBO session)
- alert your calls by hand if necessary. You can define shortcuts for the frequently used phrases and use them while entering explanations.
- at the end of the session, press the 'Export' button and paste the clipboard content at the end of the file. Your partner should do it too.
- review with your partner all newly created alerts and make the necessary corrections

For very large files, collaborative online code editors are preferred like https://cryptpad.fr/code/.

This way, the file is ready for the next session and will contain recently alerted calls.

The best method to learn BBOalert is to create a teaching table and to experiment with data.

## Data file format

The file must begin with the <b>BBOalert</b> keyword (case insensitive) to be recognized by the program.

Comma separated value (CSV) format is used for each record.

Alerted calls should contain at least three text fields separated by commas :

    <context>,<call>,<explanation>[,optional text ignored by BBOalert]
    
where "context" is the bidding sequence preceding the "call". In those two fields we use two-character self-explaining tokens :

    1C 1D 1H 1S 1N Db Rd 2C 2D ....
    
To increase the readability of the code :
- we use '--' token for pass instead of 'Pa'
- outside of the data records free text is allowed for documentation purposes
- leading and trailing spaces and tabs are allowed in all fields.
- spaces are allowed in the context field

### Examples

#### Opening bid

    ,1N,12-14p balanced

Note :
- empty "context" field in the first record, because there is no bid before the opening
- Eventual passes preceding the opening are ignored

#### Development

    1N--,2C,Stayman can be weak
    1N--2C--,2D,No 4 card major

Note : -- codes mean pass by opponents

#### Development with opponents overcall

    1HDb,Rd,9+p misfit !H penalty redouble

#### Overcall

    1D,2D,Major two-suiter

### Advanced features

#### Seat-dependent openings

An empty "context" field means seat-independent opening. By using leading -- codes you can define seat-dependent opening. Placed after seat independent opening code, it will override it for the specified seat. Example
    
    ,1S,12-21p 5+!S,    This is the normal opening for all seats
    ----,1S,8-21 5+!S,    except after two passes. It can be weaker
    ----1S--,2C,Drury,    in such a case Drury is used

The alternative method of coding seat-dependent openings is presented in the section "Optional code".
 
#### Continued context

If the context is identical with the previous record, the '+' character can be used in the "context" field

Example : instead of code

    1N--,    2C,    Stayman
    1N--,    2D,    Texas !H
    1N--,    2H,    Texas !S
    
you can use code

    1N--,    2C,    Stayman
    +,    2D,    Texas !H
    +,    2H,    Texas !S
    
#### Long explanation text

If you need more than 39 characters to explain the alerted call, the solution is to place in the middle of the text the '#' character. It will split the text into two parts : the first will be used in the explanation field of the bidding box. The second part will be set in the chat box. The chat message should be sent to the opponents to complete the alert procedure.

Example :

    1S,2C,Please read chat for explanation#Natural overcall with at least a decent 5-card suit

#### Wild cards

In the cases where the meaning of the call is not influenced by an eventual overcall, wildcards can be used in the "context" field. This can make the code more readable and more compact. Two characters are allowed as wildcard '*' or '_'. They match one character and have the same effect. In this example :

    1N__,2H,Transfer->!S
    
the code means : whatever the opponents do, 2H remains a mandatory transfer to 2S. Otherwise code should be provided for all possible overcalls made by the opponents.

### Optional code

Almost everyone on BBO is using the SAYC bidding system. But SAYC is not the world standard and some opponents will use another bidding system such as ACOL or French Standard. If you play on BBO with your partner to practice a sophisticated defense system - with particular agreements that depend on the conventions used by the opponents - you must be able to switch on-the-fly between different defense options during the game.

To solve this problem, the keyword 'Option' followed by the option name are used. The optional block of code is ended by another optional block or by bare 'Option' keyword. The selectable options will be displayed at the left side of the screen.

The subsequent options with the common prefix word will be grouped automatically. Within the group only one option can be selected to avoid conflicting codes. You are free to disable any option. Initially the first member of each group is enabled.

It is recommended to provide all overcalls in optional code blocks for each possible opening. This will allow you to unselect portions of code if necessary.

Optional blocks of data can be used also for :
- vulnerability-dependent openings by using @n or @v tags
- seat-dependent openings by using @1 @2 @3 and @4 tags. Seat dependent overcalls must be coded explicitely as in the example :

        --1D,1H,<explanation text>

This is 3rd seat overcall not 3rd seat opening. 

The selection is done automatically if the block name contains any @ tag. This selection can be then manually overridden by the user during the game. Combining tags is allowed. In this example :

    Option,Opening @v@3@4

the option will be enabled if vulnerable in 3rd or 4th seat.

Options can be selected with a menu which is normally hidden. To toggle the display of this menu, use the 'Options' button.

Example :


    Option,NT 15-17
        1N,Db,any 6 card suit (DONT)    
    Option,NT 12-14
        1N,Db,for penalties
    Option,2H weak
        ... code specific for the defense against weak-2 opening
    Option,2H weak 5!H and 4+m
        ... code specific for the defense against Muiderberg opening
    Option,MyOpenings @n
        ,1N,12-14 balanced
    Option,MyOpenings @v
        ,1N,15-17 balanced
    Option

In this example three separated groups of options are created.

### Shortcuts

Shortcut format :

    Shortcut,<token>,<full text>
    
In this example :

    Shortcut,TH,Texas->!H
    
TH string will be immediately expanded to the "Texas->!H" during text entry in the Message or Explanation text box. The tokens can be of any length , but we advise to use uppercase two-character tokens to avoid confusion during normal text entry.

You are also allowed to define Alt-key shortcuts as shown in this example :

    Shortcut,AltA,this text will be inserted if you press Alt-A key
    
Note : check for potential conflicts with Alt key shortcuts of the browser.

### Full Disclosure BSS file support

BBOalert can read BSS files in the same way as native BBOalert :

- open the BSS file with a text editor
- select all text and copy it to the clipboard
- in BBOalert use 'Import' button.

BBOalert converts BSS data internally to the BBOalert native format. Vulnerability-dependent calls are supported (@n or @v tag in the optnion name). Seat-dependent openings are set in separate optional blocks (@1 @2 @3 or @4 tag in the option name).

The 'Export' button will write the converted data to the clipboard. You can paste it into the text editor and use it as a starting point for further modifications. Another possible scenario is to keep importing the original BSS file and to create an overriding code (in BBOalert native format) in a separate file to be appended later ('Append' button).
