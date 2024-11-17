# Humoyun Abdumavlon - Economics Ph.D. Student

<!-- Navigation -->
<nav class="fixed top-0 left-0 right-0 z-50 bg-white shadow-md">
  <div class="flex justify-between items-center px-10 py-4 max-w-7xl mx-auto">
    <a href="#" class="text-gray-800 text-2xl hover:text-primary font-bold transition-colors">
      Humoyun Abdumavlon
    </a>
    <ul class="hidden md:flex space-x-8" id="nav-menu">
      <li><a href="#home" class="text-gray-800 hover:text-primary transition-colors">Home</a></li>
      <li><a href="#research" class="text-gray-800 hover:text-primary transition-colors">Research</a></li>
      <li><a href="#teaching" class="text-gray-800 hover:text-primary transition-colors">Teaching</a></li>
      <li><a href="#contact" class="text-gray-800 hover:text-primary transition-colors">Contact</a></li>
    </ul>
    <button class="md:hidden text-2xl" onclick="toggleMenu()">☰</button>
  </div>
</nav>

<!-- About Section -->
<section id="home" class="pt-[140px] pb-1">
  <div class="max-w-7xl mx-auto px-4">
    <div class="flex flex-col md:flex-row gap-8 items-start">
      <!-- Profile Picture -->
      <div class="w-full md:w-1/3">
        <img src="profile.jpg" alt="Profile Picture" class="w-[270px] h-[270px] rounded-full object-cover mx-auto" style="object-position: center -20px" />
        <div class="text-center mt-6">
          <h2 class="text-[1.75em] font-light text-black mb-2">Humoyun Abdumavlon</h2>
          <h3 class="text-xl font-light text-gray-600 mb-2">Ph.D. Student in Economics</h3>
          <h3 class="text-xl font-light mb-2">
            <a href="https://www.econ.pitt.edu/" class="text-primary hover:underline">University of Pittsburgh</a>
          </h3>
          <div class="flex justify-center items-center space-x-8">
            <a href="cv.pdf" class="text-3xl text-primary transition-colors"><i class="ai ai-cv"></i></a>
            <a href="mailto:abdumavlon@pitt.edu" class="text-3xl text-primary transition-colors"><i class="fas fa-envelope"></i></a>
            <a href="https://github.com/humoyunabdumavlon" class="text-3xl text-primary transition-colors"><i class="fab fa-github"></i></a>
            <a href="https://www.linkedin.com/in/humoyun-abdumavlon" class="text-3xl text-primary transition-colors"><i class="fab fa-linkedin"></i></a>
          </div>
        </div>
      </div>

      <div class="w-full md:w-2/3">
        <p class="text-xl text-gray-800">
              I am a third-year Ph.D. student in Economics at the University of Pittsburgh, 
              specializing in political economy and development economics. 
              My research focuses on the interplay between conflict, institutions, and religion, 
              with a particular interest in their implications for economic development and governance.
        </p>

        <div class="flex flex-col md:flex-row gap-8 mt-8">
          <div class="md:w-2/5">
            ### Interests
            
            - **Empirical Political Economy**
            - **Development Economics**
            - **Public Economics**
          </div>

          <div class="md:w-3/5">
            ### Education
            
            <div class="space-y-4">
              <div class="flex items-start">
                <i class="fas fa-graduation-cap text-lg text-primary mr-3"></i>
                <div>
                  **Ph.D. in Economics, 2027 (expected)**  
                  [University of Pittsburgh](https://www.econ.pitt.edu/)
                </div>
              </div>
              <div class="flex items-start">
                <i class="fas fa-graduation-cap text-lg text-primary mr-3"></i>
                <div>
                  **M.A. in Economics, 2023**  
                  [University of Pittsburgh](https://www.econ.pitt.edu/)
                </div>
              </div>
              <div class="flex items-start">
                <i class="fas fa-graduation-cap text-lg text-primary mr-3"></i>
                <div>
                  **M.Sc. in Economics, 2022**  
                  [University of Virginia](https://www.commerce.virginia.edu/)
                </div>
              </div>
              <div class="flex items-start">
                <i class="fas fa-graduation-cap text-lg text-primary mr-3"></i>
                <div>
                  **B.Sc. in Economics, 2020**  
                  [Tufts University](https://www.westminster.ac.uk/)
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- Scripts and Styles -->
<script src="https://cdn.tailwindcss.com"></script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css" />
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/jpswalsh/academicons@1/css/academicons.min.css" />

<script>
tailwind.config = {
  theme: {
    extend: {
      colors: {
        primary: "#1565c0",
      },
      fontFamily: {
        sans: [
          "-apple-system",
          "BlinkMacSystemFont",
          "Segoe UI",
          "Roboto",
          "Oxygen",
          "Ubuntu",
          "Cantarell",
          "Open Sans",
          "Helvetica Neue",
          "sans-serif",
        ],
      },
    },
  },
};

function toggleMenu() {
  const mobileMenu = document.getElementById("mobile-menu");
  const isOpen = mobileMenu.style.transform === "translateY(0px)";
  mobileMenu.style.transform = isOpen ? "translateY(-100%)" : "translateY(0)";
}

document.querySelectorAll("#mobile-menu a").forEach((link) => {
  link.addEventListener("click", () => {
    const mobileMenu = document.getElementById("mobile-menu");
    mobileMenu.style.transform = "translateY(-100%)";
  });
});

// Navigation highlighting
const sections = document.querySelectorAll("section");
const navLinks = document.querySelectorAll(".nav-links a");

function highlightNavigation() {
  let currentSection = '';
  const scrollPosition = window.scrollY + window.innerHeight / 3;

  sections.forEach((section) => {
    const sectionTop = section.offsetTop;
    const sectionHeight = section.clientHeight;
    if (scrollPosition >= sectionTop && scrollPosition < sectionTop + sectionHeight) {
      currentSection = section.getAttribute("id");
    }
  });

  navLinks.forEach((link) => {
    const href = link.getAttribute("href").substring(1);
    if (href === currentSection) {
      link.classList.add("text-primary", "font-medium");
    } else {
      link.classList.remove("text-primary", "font-medium");
    }
  });
}

let isScrolling;
window.addEventListener("scroll", () => {
  window.clearTimeout(isScrolling);
  isScrolling = setTimeout(highlightNavigation, 50);
});

highlightNavigation();
setTimeout(highlightNavigation, 100);
</script>

<style>
html { scroll-behavior: smooth; }
</style>
