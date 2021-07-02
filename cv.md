# Aleksandr Seryapin 

![photo](CVphoto_small.jpg)

**Date:** of birth: 20.12.1986  
**Addres:** Saint-Petersburg  
**Family Status:** married    
**Mobile:** +7 (921) 581-69-65  
**Email:** *al_seryapin@mail.ru*  

## PERSONAL PROFILE:
I am Electronics Engineer with experience of programming microcontrollers and supporting sales web sites. Now I am working at changing my specialization to JavaScript Full Stack Developer. I have finished «Interface development: layout and JavaScript” course run by Yandex and MIPT and now participating course from RS-School. In my previous jobs I have learned how to conduct negotiations in English and Russian language, provide presentation, business writing, time management, setting goal, managing people and other skills which could be useful in any sphere.  


## EDUCATION:  
2004-2009 **Ryazan State Radio Engineering University, Ryazan, Russia**  
**Specialization:**  Design electrical equipment and power supply system of electrical equipment.  
**Graduation paper:** Microcontroller-based motor controller for wire feed unit   

<<<<<<< Updated upstream
12.2020 - 06.2021	Course **“Interface development: layout and JavaScript”** run by Moscow Institute of Physics and Technology   
=======
12.2020 - 06.2021	Course **“Interface development: layout and JavaScript”** run by Moscow Institute of Physics and Technology    
>>>>>>> Stashed changes
07.2021 - present	Course **“JavaScript Front-end”** run by Rolling Scopes School

## KNOLEDGE
* JavaScript, Node.js, C
* Visual Studio Code, Version control Git
* HTML5, CSS3,
* Responsive design, browsing developer tools

## ENGLISH SKILLS
Upper-Intermediate (B2) level  of English.    
Experience of conducting technical and commercial negotiations, provide presentations, oral translation for customers during tripartite meeting. 


## WORK EXPERIENCE:  
08.2017 – present  **["EFO" LLC"](http://efo.ru/)**  
**Position:** Head of Power Management Unit.  
**Main responsibilities:** Promotion of power supplies units for Russian market; website support: filling with content and creating landing pages; negotiations with foreign manufactures; technical support of customers and integration troubleshooting; 

06.2015 – 08.2017  **["PeterburgElectronComplekt" LLC](http://pec.ru)**  
**Position:** Brand Manager.  
**Main responsibilities:** Promotion of electronic components for demanding applications; website support: filling with content; technical support of customers and integration troubleshooting; organizing and translating technical seminars with foreign manufactures; communication with region sales managers of foreign manufacturers; preparation of marketing plans.

01.2015 – 06.2015  **[TET ESTEL, Tallinn](http://www.tet-estel.com/)**   
**Position:** Project engineer of avionic ground power supply unit.  
**Main responsibilities:** Making requirements specifications for new equipment; managing design team (designers, engineers, programmers); making gesign plans; choosing key electronics components; project control.

08.2011 – 01.2015  **[NIPK “Electron”, Co., Saint-Petersburg, Russia](http://electronxray.com/)**  
**Position:** Electrical engineer, high voltage power supply group  
**Main responsibilities:** Designing of medical X-ray equipment; preparation of technical documentation; writing of technical documentation. requirements specifications for mechanical design engineer and programming engineer.

<<<<<<< Updated upstream
06.2008 – 07.2011	**[“NPP FEB”, Ltd.](http://www.feb.spb.ru/)**   
**Position:** Electrical engineer, research and development unit.
=======
06.2008 – 07.2011	**[“NPP FEB”, Ltd.](http://www.feb.spb.ru/)**
**Position:** Electrical engineer, research and development unit.    
>>>>>>> Stashed changes
**Main responsibilities:**Programming microcontrollers by “C”; designing of welding equipment including MIG/MAG, TIG, MMA and wire feed; managing engineers; preparation of technical documentation.


## ADDITIONAL INFORMATION:
Experienced in managing people.   
Driving license, category B.

## CODE EXAMPLE:
```javascript
/** Constructor of Snakes and Ladder game for two players */
function SnakesLadders() {
  this.curentPlayer = "1";
  this.player1 = 0;
  this.player2 = 0;
  this.gameOver = false;
            /* 0  1   2   3   4   5   6   7   8   9  10*/
  this.board =[0, 0 , 38, 0 , 0 , 0 , 0 , 14, 31, 0 , 0,
                  0 , 0 , 0 , 0 , 26, 6 , 0 , 0 , 0 , 0, /*10*/
                  42, 0 , 0 , 0 , 0 , 0 , 0 , 84, 0 , 0, /*20*/
                  0 , 0 , 0 , 0 , 0 , 44, 0 , 0 , 0 , 0, /*30*/
                  0 , 0 , 0 , 0 , 0 , 25, 0 , 0 , 11, 0, /*40*/
                  67, 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0, /*50*/
                  0 , 19, 0 , 60, 0 , 0 , 0 , 0 , 0 , 0, /*60*/
                  91, 0 , 0 , 53, 0 , 0 , 0 , 98, 0 , 0, /*70*/
                  0 , 0 , 0 , 0 , 0 , 0 , 94, 0 , 68, 0, /*80*/
                  0 , 88, 0 , 0 , 75, 0 , 0 , 0 , 80, 0] /*90*/
};
/** One rolling of the dies  
  * @param {number} die1 - the number of die1 
  * @param {number} die2 - the number of die2 
  * @return {string} "Player n is on square n" 
  *                  or "Player n Wins!" when player on 100th square.
  *                  or ""Game over!" when privious player already won.
  */
SnakesLadders.prototype.play = function (die1, die2) {
  let out = "nope";
  if (this.gameOver) { return "Game over!" }
    else {
      out = this.forvard(die1 + die2);
      this.isWinner();
      this.isDouble(die1, die2);
    }
  return out;
}

 /**
 * Do certain steps forward.
 * @param {number} number - The sum of dies.
 * @return {string} to function play()"Player n is on square n" or "Player n Wins!" when player on 100th square.
 */
SnakesLadders.prototype.forvard = function (number) {
  let out = "";
  if (this["player" + this.curentPlayer] + number > 100) {
    this["player" + this.curentPlayer] = 100 - (this["player" + this.curentPlayer] + number - 100)
    }
    else { this["player" + this.curentPlayer] += number };
  this.ifSnakeOrLadder();
  if (this.isWinner()) { out = `Player ${this.curentPlayer} Wins!` }
    else { out = `Player ${this.curentPlayer} is on square ${this["player" + this.curentPlayer]}` }
  return out;
};

 /**
 * Check if current playear reach 100th square
 * change gameOver flag in ninja style :)
 * @return {boolean} true if current playear reach 100th square
 */
SnakesLadders.prototype.isWinner = function () {
  if (this["player" + this.curentPlayer] == 100) {
    this.gameOver = true;
    return true;
  }
};

/**
 * Check if current playear step on square with snake head or ladder bottom
 * if true moving current player by snake or ladder 
 */
SnakesLadders.prototype.ifSnakeOrLadder = function () {
  if (this.board[this["player" + this.curentPlayer]] != 0) { this.moveTo(this.board[this["player" + this.curentPlayer]]) }
};

/** Moving curent player directly to certain square
 * @param {number} number - the number of square (tail of snake or top of ladder)
 */
SnakesLadders.prototype.moveTo = function (number) {
  this["player" + this.curentPlayer] = number;
};

/** Cheking if roll double 
 * changes the player in a ninja style ;)
 * @param {number} die1 - the number of die1 
 * @param {number} die2 - the number of die2 
 */
SnakesLadders.prototype.isDouble = function (die1, die2) {
  if (die1 == die2) { }
    else { this.nextPlayer() };
};

/** Change the player */
SnakesLadders.prototype.nextPlayer = function () {
  if (this.curentPlayer == 1) { this.curentPlayer = 2 }
    else { this.curentPlayer = 1 };
};
```



