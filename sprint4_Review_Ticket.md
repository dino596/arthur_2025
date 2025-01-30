---
layout: post
title: Sprint 4 Review Ticket
description:  Review Ticket for Sprint 4
type: issue
permalink: /sprint4
comments: true
---

MY SPRINT 4 OBJECTIVES: [github](https://github.com/nighthawkcoders/portfolio_2025/issues/622#issuecomment-2552724061)<br>

My biggest project this Sprint has been my mines project, which is a mainly individual project, but connects with Portfolio as a whole with Casino and Gamify.<br>
<br>
My backend has been mostly functional since winter break, and thus this times changes were very simple, completely migrating from localhost to javaURI and ensuring the connection works.<br>
In addition, due to the migration of the login system from email to GHID, I also needed to adapt to that change.<br>
Notable commit: [github](https://github.com/CSA-Coders-2025/CSA_Combined_Backend_Fork/commit/c7bd9e8d27d64abf668cb5facb118d6872b53608)<br>
<br>
[![image.png](https://i.postimg.cc/pLXMYJgq/image.png)](https://postimg.cc/Czt2wkMq)<br>
[![image.png](https://i.postimg.cc/YSTc7Kjs/image.png)](https://postimg.cc/zLw2wQCC)<br>
[![image.png](https://i.postimg.cc/SRpwX66L/image.png)](https://postimg.cc/phq04n1y)<br>
<br>
My frontend had to undergo more changes.<br>
I completely revamped my frontend design to make it more bearable to look at (my css is not perfect yet, more changes will come).<br>
When submitting bet:<br>
[![image.png](https://i.postimg.cc/zDnssQNx/image.png)](https://postimg.cc/gr2tRNnh)<br>
When picking squares (green is success, red is bomb)<br>
[![69-B16-D90-5642-4-E49-B629-6-E730199-BECE.png](https://i.postimg.cc/T3SNLjGy/69-B16-D90-5642-4-E49-B629-6-E730199-BECE.png)](https://postimg.cc/WdGwxkdj)<br>
Notable commit: [github](https://github.com/CSA-Coders-2025/CSA_Combined_Frontend_Fork/commit/c05ac5612e9bd76b1f6597b1bdb70d7ffaefc4fc)<br>
A quick CSS commit: [github](https://github.com/CSA-Coders-2025/CSA_Combined_Frontend_Fork/commit/b7c8f05ba40462fb2775e4f1299a700a103b3fc3)<br>
<br>
Most importantly, I fixed my connection with the person database.<br>
JWT Token<br>
[![48-B2-A897-73-ED-4-A9-B-B7-AB-15-A37756-CDAC.png](https://i.postimg.cc/gktCNDMk/48-B2-A897-73-ED-4-A9-B-B7-AB-15-A37756-CDAC.png)](https://postimg.cc/7f7tLg8p)<br>
JavaURI with UID (instead of email)<br>
[![image.png](https://i.postimg.cc/0jfHbL2x/image.png)](https://postimg.cc/YLvxPDWy)
<br><br>
I was also able to log into the student toolkit login<br>
[![700-F2-C20-268-B-4-E20-BAB8-69-A66-EDE73-CF.png](https://i.postimg.cc/15ZQ4qs5/700-F2-C20-268-B-4-E20-BAB8-69-A66-EDE73-CF.png)](https://postimg.cc/qgQY5gN9)<br>
Using the student toolkit, I was able to submit my HW for 2D Arrays pt. 2<br>
[![E7-EA59-BB-9724-453-F-903-D-69478-F3-B92-A1.png](https://i.postimg.cc/DzSDxvnM/E7-EA59-BB-9724-453-F-903-D-69478-F3-B92-A1.png)](https://postimg.cc/GB1q21BF)
<br><br>
1/30/2025<br>
[Draw.io diagram](https://github.com/CSA-Coders-2025/CSA_Combined_Backend_Fork/blob/casinobranch/src/main/java/com/nighthawk/spring_portfolio/mvc/casino.drawio), made with Saaras Kodali<br>
[![B88-C4-EF2-C1-F9-4192-8-D3-C-2-D554-D18-D876.png](https://i.postimg.cc/8zQfyVQL/B88-C4-EF2-C1-F9-4192-8-D3-C-2-D554-D18-D876.png)](https://postimg.cc/ppCdT4dd)<br>
Your diagram represents the **Casino branch of Gamify**, focusing on the **Mines** and **Poker** games. It illustrates class relationships and API endpoints involved in handling game logic and communication with clients.

---

### **1. Overview of Components**
The diagram is structured into three main sections:
- **Mines Game (Top Section)**
- **Poker Game (Middle and Bottom Sections)**
- **Casino System (Left Section)**

Each section contains Java classes and API controllers that interact with each other.

---

### **2. Breakdown of Components**

#### **Casino System (General)**
- **"Casino branch of Gamify"**  
  - Represents the overarching system managing casino games.
  - Connects to the **MinesApiController** and **PokerApiController**.

#### **Mines Game**
- **MinesApiController.java**
  - API Controller handling HTTP requests.
  - Endpoints:
    - `/api/casino/mines`
    - `/api/casino/mines/{xCoord}/{yCoord}` → Check position for a mine.
    - `/api/casino/mines/stakes/{stakes}` → Set stake amount.
    - `/api/casino/mines/balance/{uid}` → Get user balance.
    - `/api/casino/mines/winnings` → Get winnings.

- **MinesBoard.java**
  - Represents the **Mines game board**.
  - Attributes:
    - `int[][] board` → Stores mine positions.
    - `int stakes`
    - `int xCoord, yCoord`
  - Methods:
    - `placeMines()` → Places mines on the board.
    - `checkMines(int xCoord, int yCoord)` → Checks if a position has a mine.
    - `winnings()` → Calculates winnings.
  - The **MinesApiController** communicates with **MinesBoard.java** to process game logic.

---

#### **Poker Game**
- **PokerApiController.java**
  - API Controller handling poker-related HTTP requests.
  - Endpoints:
    - `/api/casino/poker`
    - `/api/casino/poker/play`
    - `/api/casino/poker/reset`

- **PokerBoard.java**
  - Represents the **Poker game board**.
  - Attributes:
    - `List<PokerCard> deck`
    - `List<PokerCard> playerHand`
    - `List<PokerCard> dealerHand`
  - Methods:
    - `initializeDeck()` → Sets up a new deck.
    - `shuffleDeck()` → Shuffles the deck.

- **PokerCard.java**
  - Represents a **single poker card**.
  - Attributes:
    - `String rank`
    - `String suit`
  - Methods:
    - `getRank()`, `getSuit()`
    - `compareTo(PokerCard other)` → Compares card values.
    - `getCardRankValue()` → Returns the card's rank as a numerical value.

- **PokerBetRequest.java**
  - Handles **player bets**.
  - Attributes:
    - `int bet`
  - Methods:
    - `getBet()`
    - `setBet()`
  - Used by **PokerApiController** to process betting requests.

- **PokerGameResult.java**
  - Handles **game results**.
  - Methods:
    - `isPlayerWin()`
    - `isDealerWin()`
    - `getWinnings()`
    - `evaluateHand(List<PokerCard> hand)`

- **Relationships:**
  - **PokerApiController** interacts with **PokerBoard** and **PokerGameResult**.
  - **PokerBoard** relies on **PokerCard** for card-related operations.

---

### **3. Relationship Arrows**
- **API controllers (MinesApiController, PokerApiController)**
  - Communicate with their respective game logic classes (**MinesBoard**, **PokerBoard**, etc.).
- **PokerBoard → PokerCard**
  - PokerBoard uses PokerCard to manage the deck.
- **PokerApiController → PokerGameResult**
  - The API controller queries **PokerGameResult** to determine winners.

---

### **4. Summary**
- **Mines and Poker games** have separate logic and API controllers.
- **MinesApiController** processes mines-related requests and interacts with **MinesBoard**.
- **PokerApiController** handles poker-related operations and interacts with **PokerBoard**, **PokerBetRequest**, and **PokerGameResult**.
- The **PokerBoard** is responsible for managing the game deck and hands.
- **PokerCard** provides individual card properties and comparison methods.
- **PokerGameResult** evaluates poker hands and determines winners.


