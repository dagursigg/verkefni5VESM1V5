## lokaverkefniVESM1V5

- Hópur : ***Dagur Sigurðsson*** og ***Viktor Frans***.
-  VESM1, Tölvubraut, Tækniskólinn.

---

### Stepper Mótor Tilraun 1 með línulegri hreyifinu.
- Sett var saman hreyfilegann mótor í tíma, hermt var eftir módeli frá kennara og allir partar og verkfæri, gaf kennari.
- [Myndband af virkni ***(https://youtu.be/KcXzey425uk)***]

---

### Stepper Mótor Tilraun 2 með hreyfingu beggja hjóla og virkni beggja mótora.
- Bætt var við öðrum mótori, og einu öðru hjóli, einnig þurfti að tengja annað arduino til þess að virkja mótorinn.

- ![Mynd sem sýnidæmi](https://github.com/dagursigg/verkefni6/blob/main/ho.png%20(1).png)

- [Myndband af þeirri virkni ***(https://youtu.be/mvp8isAVO0I***)]

---
## Kóði
- ### Hér er kóðinn sem notaður var í verkefnið, honum var breytt að vild í s.s. hraða, tengingu afli og fleira.
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
