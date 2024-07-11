# WoTech_Team12

Learning repository about Python, Java, Github.

## About Us
We are Team 12, a dynamic and collaborative group of four women from the WoTech program. United by our passion for technology and innovation, we work together to learn, grow, and excel in the IT field.

### Team Members
☀ **Gita Rācenāja** (GitaRac), Latvia (Tukums)

☀ **Daiga Lejiņa** (MsLejina), Latvia (Riga) and Brussels

☀ **Heili Roos** (heiliroos), Estonia (Haapsalu)

☀ **Christin Algo** (cchristinalgo), Estonia (Viljandi)

## Communication
We use Discord to collaborate and discuss WoTech learning realated topics.

# Teamwork
## Git & GitHub

[GitHub - push, pull, commit, add code.pdf](https://github.com/user-attachments/files/16177869/GitHub.-.push.pull.commit.add.code.pdf)

## Java **API endpoints** 11.07.2024.
InteliiJ:
```java
package com.datorium.Datorium.API;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.CrossOrigin;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

@SpringBootApplication
@RestController
@CrossOrigin
public class DatoriumApiApplication {

	public static void main(String[] args) {
		System.out.println("asd");
		SpringApplication.run(DatoriumApiApplication.class, args);
	}


	@GetMapping("/ping")
	public String ping() {
		return "pong";
	}

	@GetMapping("/hello")
	public String hello(@RequestParam(value = "name", defaultValue = "World") String name) {
		return String.format("Hello %s!", name);
	}

	@GetMapping("/sum")
	public int sum(@RequestParam(value = "number1") int number1, @RequestParam(value = "number2") int number2){
		return number1 + number2;
	}

	@GetMapping("/multiply")
	public int multiply(@RequestParam(value = "number1") int number1, @RequestParam(value = "number2") int number2){
		return number1 * number2;
	}


	@GetMapping("/team12")
	public String[] team() {
		String[] team12 = {"Gita", "Daiga", "Heili", "Christin"};
		return team12;
	}

	@GetMapping("/team12/member")
	public String getTeamMember(@RequestParam(value = "index", defaultValue = "0") int index) {
		String[] team12 = {"Gita", "Daiga", "Heili", "Christin"};
		if (index >= 0 && index < team12.length) {
			return team12[index];
		} else {
			return "Index out of bounds";
		}
	}

	@GetMapping("/mycats")
	public String[] mycats(){
		String[] mycats = {"Bonita", "Elsa"};
		return mycats;
	}
}
```
	http://localhost:8080/sum?number1=17&number2=13
	http://localhost:8080/multiply?number1=100&number2=13
	http://localhost:8080/team12
	http://localhost:8080/team12/member?index=2
	http://localhost:8080/mycats






