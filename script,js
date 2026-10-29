
// Get the search box and all course cards

let searchInput = document.getElementById("searchInput");

let courses = document.querySelectorAll(".course-item");

let filterButtons = document.querySelectorAll(".filter-btn");

let noResults = document.getElementById("noResults");

let selectedCategory = "all";


// Function to search and filter courses

function filterCourses() {

    let searchText = searchInput.value.toLowerCase();

    let visibleCourses = 0;

    courses.forEach(function(course) {

        let courseText = course.innerText.toLowerCase();

        let courseCategory = course.dataset.category;

        let matchesSearch = courseText.includes(searchText);

        let matchesCategory =
            selectedCategory === "all" ||
            courseCategory === selectedCategory;

        if (matchesSearch && matchesCategory) {

            course.style.display = "";

            visibleCourses++;

        } else {

            course.style.display = "none";

        }

    });

    // Show a message if no courses match

    noResults.hidden = visibleCourses !== 0;

}


// Search when the user types

searchInput.addEventListener("input", filterCourses);


// Filter courses by category

filterButtons.forEach(function(button) {

    button.addEventListener("click", function() {

        selectedCategory = button.dataset.category;

        // Remove active class from every button

        filterButtons.forEach(function(btn) {
            btn.classList.remove("active");
        });

        // Highlight the selected button

        button.classList.add("active");

        filterCourses();

    });

});


// Open the selected course in a Bootstrap modal

let watchButtons = document.querySelectorAll(".watch-btn");

let courseModal = document.getElementById("courseModal");

let modalTitle = document.getElementById("modalTitle");

let modalVideo = document.getElementById("modalVideo");

let modal = new bootstrap.Modal(courseModal);


watchButtons.forEach(function(button) {

    button.addEventListener("click", function() {

        let title = button.dataset.title;

        let videoId = button.dataset.video;

        modalTitle.textContent = title;

        modalVideo.src =
            "https://www.youtube.com/embed/" +
            videoId +
            "?autoplay=1";

        modal.show();

    });

});


// Stop the video when the modal is closed

courseModal.addEventListener("hidden.bs.modal", function() {

    modalVideo.src = "";

});


// Contact form demonstration

let contactForm = document.getElementById("contactForm");

let formMessage = document.getElementById("formMessage");


contactForm.addEventListener("submit", function(event) {

    event.preventDefault();

    formMessage.textContent =
        "Thank you! Your message has been submitted.";

    formMessage.className = "mt-3 text-success";

    contactForm.reset();

});
