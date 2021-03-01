# lokaverkefniVESM1V5

- Hópur : ***Dagur Sigurðsson*** og ***Viktor Frans***.
-  VESM1, Tölvubraut, Tækniskólinn.

---

### Stepper Mótor Tilraun 1 með línulegri hreyifinu.
- Sett var saman hreyfilegann mótor í tíma, hermt var eftir módeli frá kennara og allir partar og verkfæri voru gefin frá kennara.
- Til þess að sjá myndband af virkninni, ýttu [hér](https://youtu.be/KcXzey425uk)

---

### Stepper Mótor Tilraun 2 með hreyfingu beggja hjóla og virkni beggja mótora.
- Bætt var við öðrum mótori, og einu öðru hjóli, einnig þurfti að tengja annað arduino til þess að virkja mótorinn.
 
- Til þess að sjá myndband af þessari virkni ýttu [hér](https://youtu.be/mvp8isAVO0I)

- Mynd af þeirri virkni.
- ![Mynd sem sýnidæmi](https://github.com/dagursigg/verkefni6/blob/main/ho.png%20(1).png)


---
## Kóði
- #### Hér er kóðinn sem notaður var í verkefnið, honum var breytt að vild í s.s. hraða, tengingu afli og fleira.
```C
// Include the AccelStepper Library
#include <AccelStepper.h>

// Define step constant
#define FULLSTEP 4

// Creates an instance
// Pins entered in sequence IN1-IN3-IN2-IN4 for proper step sequence
AccelStepper myStepper(FULLSTEP, 8, 10, 9, 11);

void setup() {
	// set the maximum speed, acceleration factor,
	// initial speed and the target position
	myStepper.setMaxSpeed(1000.0);
	myStepper.setAcceleration(50.0);
	myStepper.setSpeed(200);
	myStepper.moveTo(2038);
}

void loop() {
	// Change direction once the motor reaches target position
	if (myStepper.distanceToGo() == 0) 
		myStepper.moveTo(-myStepper.currentPosition());

	// Move the motor one step
	myStepper.run();
}
```
---

# Seinni partur verkefnis.
### Mótor af eigin hugmynd
---
- Hugmynd okkar var mjög einfold, gera klemmu sem væri hægt að hreyfa á marga vegu.
- Hér er myndband sem við fengum hugmyndina frá og ætluðum að gera sömu virkni og hún, [hér](https://www.youtube.com/watch?v=JFFHzGBWSE4)
- Við vorum alltof lengi á þrepi eitt, að gera klemmuna sjálfa og það tók eiginlega allan tímann okkar.
- Hér eru myndir af klemmum okkar og smá til þess að sýna hvernig við festum þær.
- ![](https://github.com/dagursigg/verkefni6/blob/main/klemma%2Cfyrir.jpeg)
- ![](https://github.com/dagursigg/verkefni6/blob/main/klemma%2Ceftir.jpeg)
---
## Myndskeið af virkni verkefnis og hugmyndir þess.
- [Hér](https://youtu.be/qnDYzmQS4d4) er virkni af klemmunum og já, þetta tók allan tímann.
- [Hér](https://youtu.be/XxAMAkoekEw) er verið að setja mótorinn upp í lok tímans til þess að reyna smá að klára.
- [Hér](https://youtu.be/AjB4fP681VQ) svo smá í lokinn til þess að sýna hvað við vorum að reyna klára.
