    // DARK MODE
    document.getElementById("themeBtn").addEventListener("click", () => {
        document.body.classList.toggle("dark-mode");
    });

    // EDIT JOB TITLE
    document.getElementById("editJobBtn").addEventListener("click", () => {
        const newTitle = prompt("Enter new job title:");
        if (newTitle) {
            document.getElementById("jobTitle").textContent = newTitle;
        }
    });

    // TOGGLE SKILLS
    const skills = document.querySelector(".skills");
    const toggleSkillsBtn = document.getElementById("toggleSkillsBtn");

    toggleSkillsBtn.addEventListener("click", () => {
        if (skills.style.display === "none") {
            skills.style.display = "block";
            toggleSkillsBtn.textContent = "Hide";
        } else {
            skills.style.display = "none";
            toggleSkillsBtn.textContent = "Show";
        }
    });

    // CHARACTER COUNTER
    const msgBox = document.getElementById("msgBox");
    const counter = document.getElementById("counter");

    msgBox.addEventListener("keyup", () => {
        counter.textContent = 200 - msgBox.value.length;
    });

    // FORM VALIDATION
    function validateForm() {
        const name = document.getElementById("nameField").value.trim();
        const email = document.getElementById("emailField").value.trim();

        if (name === "" || email === "") {
            alert("Please fill in Name and Email.");
            return false;
        }

        alert("Message sent!");
        return true;
    }

    // DATE
    document.getElementById("dateDisplay").textContent =
        new Date().toDateString();

    // GREETING
    const greeting = document.createElement("p");
    const hour = new Date().getHours();

    greeting.style.fontWeight = "bold";
    greeting.textContent =
        hour < 12 ? "Good Morning!" :
        hour < 18 ? "Good Afternoon!" :
        "Good Evening!";

    document.querySelector(".content").prepend(greeting);
