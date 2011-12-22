# JS Styleguide

These are merely guidelines. They should not be adhered to mechanically,
especially if a deviation would make your code more readable.

## General

1.  Code SHOULD be indented with spaces only (not tabs).
2.  Each level of indentation SHOULD consist of 2 spaces.
3.  Lines SHOULD be 80 characters max.
4.  Code MUST use semicolons at the end of statements.

## Naming

### Overview

  Construct                                       Convention                                                  Examples
  ----------------------------------------------- ----------------------------------------------------------- ----------------------------------------------------
  Pseudoclass name (i.e., constructor function)   CamelCase with an initial capital letter                    `MightyBalrog, MagicWeapon`
  Namespace name                                  camelCase with an initial lowercase letter                  `clericSpells, savingThrows`
  Public method                                   camelCase with an initial lowercase letter                  `castDimensionalDoorway, rollForInitiative`
  Public variable                                 camelCase with an initial lowercase letter                  `materialComponents, hasTrackingAbilities`
  Private method                                  camelCase with an initial lowercase letter and underscore   `_getHealth`
  Private variable                                camelCase with an initial lowercase letter and underscore   `_backstabAbility`
  Method arguments                                camelCase with an initial lowercase letter                  `halfOrcArmy`
  Local variables                                 camelCase with an initial lowercase letter                  `isHumanoid, levelCount`
  ‘Constants’                                     Uppercase with underscores                                  `CLERIC_PLAYER, GAME_MASTER`
  Ennumeration keys                               Uppercase with underscores                                  `characterClass.MAGIC_USER, armorTypes.PLATE_MAIL`

### Notes

1.  Variable/method names in all lowercase with underscores (AKA
    'snake-case') SHOULD NOT be used unless mimicking another
    API. Object-keys received in snake-case from JSON-parsed
    API-data may be used as-is, but conversion to camel-case is
    preferred if possible.

    -   Incorrect:

            wizard_hat, vorpal_blade

    -   Correct:

            wizardHat, vorpalBlade

2.  Acronyms in variable/method names SHOULD NOT be upppercased.
    -   Incorrect:

            bartenderNPC, newRPG

    -   Correct:

            bartenderNpc, newRpg

3.  Variable/method names SHOULD be written in English.
    -   Incorrect:

            dekaiKatana

    -   Correct:

            giganticSword

4.  Variable/method names SHOULD NOT be abbreviated to the point of
    being unclear.
    -   Incorrect:

            wndMnstr[3]

    -   Correct:

            wanderingMonster[3]

## Variables

1.  Variables SHOULD be initialized at the top of function scope — if
    possible, in a way that indicates what type of value they will hold.
    Null initializations are acceptable. There should be only one `var`
    keyword, used on the first variable declaration, and subsequent
    variables should be declared using an initial comma.
    -   Incorrect:

            var magicItemCount;
            var magicSwordName = '';
            var wizardNpc;

    -   Correct:

            var magicItemCount = 0;
              , magicSwordName = ''
              , wizardNpc = null;

2.  Variable declarations SHOULD NOT include extra spaces before the
    equals sign to align the variable values.
    -   Incorrect:

            var currentThiefLevel = 8
              , canBackstab       = true
              , isNpc             = true;

    -   Correct:

            var currentThiefLevel = 8
              , canBackstab = true
              , isNpc = true;

3.  Variable names SHOULD NOT include ‘temp’ or ‘tmp’. — all local
    variables are by definition temporary.
    -   Incorrect:

            tempString, tmpDate

    -   Correct:

            str, dt

4.  Magic numbers SHOULD NOT be used. Use a constant instead.
    -   Incorrect:

            42

    -   Correct:

            ANSWER_TO_THE_QUESTION_OF_LIFE

## Coding Style

### Overview

1.  Function declaration:

        function checkForTraps(dexterity, level) {
        // Do stuff to check for traps here
        }
        var checkForSecretDoors = function (race, level) {
          // Stuff for check here
        };

2.  If statements:

        if (gotInitiative) {
          attackDragon();
        }
        else if (speaksDragon) {
          tryNegotiating();
        }
        else {
          runAway();
        }

3.  For statements:

        for (var i = 0; i < guards.length; i++) {
          rollTwentySided(guards[i]);
        }

4.  While statements:

        while (charactersInjured) {
          castCureLightWounds();
          charactersInjured = checkCharacterHealth();
        }

5.  Switch statements:

        switch (characterClass) {
          case 'ranger':
            // Ranger special stuff here
            // Fallthrough
          case 'fighter':
            // Do fighter stuff
            break;
          case 'magicUser':
            // Do mage-specific stuff
            break;
          default:
            // do nothing
        }

6.  Try-catch-finally statements:

        try {
          pickPocket();
        }
        catch(e) {
          lookInconspicuous();
          reportBack(e);
        }
        finally {
            runLikeHell();
        }

7.  Object literal:

        var obj = {
          spellName: 'Invisible Stalker'
        , numberOfFighters: 3
        , checkForTraps = function() {
            // Do trap checking
          }
        };

        var obj = {
          staff: 'Staff of the Magi'
        , wand: 'Wand of Negation'
        , misc: 'Boots of Elvenkind'
        };

### Notes

1.  Function literals MUST include a space between the word ‘function’
    and the parentheses. (Otherwise it appears to be a function with the
    name of ‘function.’)
    -   Incorrect:

            var rollInitiative = function() { // Roll die here };

    -   Correct:

            var rollInitiative = function () { // Roll die here };

2.  Line continuations should be indicated by double indentation.
    -   Incorrect:

            var localMonsterRumors = getLocalGossip(inkeeper,
                                                    localInn,
                                                    numberOfClerics,
                                                    pintsOfAlePurchased,
                                                    charismaAjustment);

    -   Correct:

            var localMonsterRumors = getLocalGossip(inkeeper,
                localInn, numberOfClerics, pintsOfAlePurchased,
                charismaAjustment);

3.  If-else statements (also while, et al) MAY be written on a single
    line, but MUST use brackets.
    -   Incorrect:

            if (isUndead) grabFire();

    -   Correct:

            if (isUndead) { grabFire(); }

4.  Parenthesis in conditional statements (if, while, for, etc.) SHOULD
    have a space before them.
    -   Incorrect:

            if(isNpc) {
              ignoreTalk();
            }

    -   Correct:

            if (isNpc) {
              ignoreTalk();
            }

5.  Parenthesis in function declarations SHOULD NOT have a space before
    them.
    -   Incorrect:

            function getArmorClass (armorType, dexterity) {
              // Get AC stuff here
            }

    -   Correct:

            function getArmorClass(armorType, dexterity) {
              // Get AC stuff here
            }

6.  Commas SHOULD be followed by spaces.
    -   Incorrect:

            getExperiencePoints(monster,hitPoints);

    -   Correct:

            getExperiencePoints(monster, hitPoints);

7.  The colon in object literal notation SHOULD have no space in front
    of it, and be followed by a single space. Entries after the initial
    item MUST be separated by leading commas (i.e., ‘comma-first’), not
    trailing commas. The opening bracket MUST NOT be dropped to a new
    line (so-called ‘Allman style’), due to automatic
    semicolon-insertion when returning an object literal. Leading commas
    should align vertically with the closing bracket on the final line.
    -   Incorrect:

            var newCharacter = {
              race:'gnome',
              class:'figheter',
              isNpc:false
            };

    -   Also incorrect:

            var newCharacter = {
              race : 'gnome',
              class : 'figheter',
              isNpc : false
            };

    -   Correct:

            var newCharacter = {
              race: 'gnome'
            , class: 'figheter'
            , isNpc: false
            };

8.  Operators SHOULD both have a space before and after.
    -   Incorrect:

            var message = speaksDrow? getMessageinDrow():'You do not speak Drow.';

    -   Correct:

            var message = speaksDrow ? getMessageinDrow() : 'You do not speak Drow.';

    -   Incorrect:

            var thaco = hit+adjustment-randomFactor;

    -   Correct:

            var thaco = hit + adjustment - randomFactor;

9.  Lengthy string parameters SHOULD be placed into variables before
    using.
    -   Incorrect:

            var elem = document.getElementById('charClass-' + charClass +
                + '_combatStats-' + armorClass + '-' + toHitBonus);

    -   Correct:

            var char = 'charClass-' + charClass;
            var combat = 'combatStatus-' + armorClass + '-' + toHitBonus;
            var elem = document.getElementById(char + '_' + combat);

