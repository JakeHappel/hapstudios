<template>
  <div id="app">
    <!-- Fixed Background Image -->
    <div
      id="background"
      class="fixed inset-0 bg-cover bg-center z-0"
      style="
        background-image: linear-gradient(
            rgba(0, 0, 0, 0.6),
            rgba(0, 0, 0, 0.6)
          ),
          url('https://images.unsplash.com/photo-1518770660439-4636190af475?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D');
      "
    ></div>

    <!-- Navigation Bar -->
    <nav class="bg-gray-900 text-white fixed w-full top-0 z-50 shadow-lg">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between h-16">
          <div class="flex items-center">
            <h1 class="text-2xl font-bold">Hap Studios</h1>
          </div>
          <div class="flex items-center space-x-4">
            <a
              v-for="section in sections"
              :key="section"
              @click="scrollTo(section.toLowerCase())"
              class="hover:text-blue-400 cursor-pointer transition duration-300"
              >{{ section }}</a
            >
            <a
              @click="scrollTo('contact')"
              class="bg-blue-600 text-white px-4 py-2 rounded-full hover:bg-blue-700 transition duration-300"
              >Get Started</a
            >
          </div>
        </div>
      </div>
    </nav>

    <!-- Home Section Content -->
    <section
      id="home"
      class="min-h-screen flex items-center justify-center text-white z-10 relative bg-transparent"
    >
      <div class="text-center max-w-3xl mx-auto px-4">
        <h2 class="text-5xl font-bold mb-4">
          Build Your Dream Website with Hap Studios
        </h2>
        <p class="text-xl mb-6">
          Transform your vision into reality with our cutting-edge web
          development and reliable hosting solutions.
        </p>
        <p class="text-lg mb-8">
          We specialize in creating stunning, functional websites tailored to
          your business needs, from simple landing pages to complex e-commerce
          platforms.
        </p>
        <a
          @click="scrollTo('contact')"
          class="bg-white text-blue-600 px-6 py-3 rounded-full font-semibold hover:bg-gray-100 transition duration-300"
          >Get a Quote</a
        >
      </div>
    </section>

    <!-- Pricing Section -->
    <section id="pricing" class="py-20 bg-gray-100 z-20 relative">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-4xl font-bold text-center mb-12">
          Website Development Pricing
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div
            v-for="plan in websitePlans"
            :key="plan.name"
            class="bg-white p-6 rounded-lg shadow-lg text-center hover:shadow-xl transition duration-300"
          >
            <h3 class="text-2xl font-semibold mb-4">{{ plan.name }}</h3>
            <p class="text-gray-600 mb-4">{{ plan.pages }}</p>
            <p class="text-3xl font-bold mb-4">{{ plan.price }}</p>
            <ul class="text-gray-600 mb-6 space-y-2">
              <li v-for="feature in plan.features" :key="feature">
                {{ feature }}
              </li>
            </ul>
            <a
              @click="scrollTo('contact')"
              class="bg-blue-600 text-white px-6 py-3 rounded-full hover:bg-blue-700 transition duration-300"
              >Choose Plan</a
            >
          </div>
        </div>
      </div>
    </section>

    <!-- Gradient Transition: Pricing to Hosting -->
    <div class="gradient-transition-pricing-hosting z-20 relative"></div>

    <!-- Hosting Section -->
    <section id="hosting" class="py-20 bg-white z-20 relative">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-4xl font-bold text-center mb-12">Hosting Plans</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <div
            v-for="plan in hostingPlans"
            :key="plan.name"
            class="bg-gray-100 p-6 rounded-lg shadow-lg text-center hover:shadow-xl transition duration-300"
          >
            <h3 class="text-2xl font-semibold mb-4">{{ plan.name }}</h3>
            <p class="text-3xl font-bold mb-4">{{ plan.price }}</p>
            <ul class="text-gray-600 mb-6 space-y-2">
              <li v-for="feature in plan.features" :key="feature">
                {{ feature }}
              </li>
            </ul>
            <a
              @click="scrollTo('contact')"
              class="bg-blue-600 text-white px-6 py-3 rounded-full hover:bg-blue-700 transition duration-300"
              >Choose Plan</a
            >
          </div>
        </div>
      </div>
    </section>

    <!-- Gradient Transition: Hosting to About -->
    <div class="gradient-transition-hosting-about z-20 relative"></div>

    <!-- About Us Section -->
    <section id="about" class="py-20 bg-gray-900 text-white z-20 relative">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-4xl font-bold text-center mb-12">About Hap Studios</h2>
        <p class="text-lg text-center max-w-3xl mx-auto">
          Hap Studios is a passionate team of web developers and designers
          dedicated to creating exceptional digital experiences. With years of
          expertise, we craft websites that not only look great but also drive
          results for your business.
        </p>
      </div>
    </section>

    <!-- Gradient Transition: About to FAQ -->
    <div class="gradient-transition-about-faq z-20 relative"></div>

    <!-- FAQ Section -->
    <section id="faq" class="py-20 bg-gray-100 z-20 relative">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-4xl font-bold text-center mb-12">
          Frequently Asked Questions
        </h2>
        <div class="space-y-6">
          <div
            v-for="faq in faqs"
            :key="faq.question"
            class="bg-white p-6 rounded-lg shadow-lg"
          >
            <h3 class="text-xl font-semibold mb-2">{{ faq.question }}</h3>
            <p class="text-gray-600">{{ faq.answer }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Gradient Transition: FAQ to Contact -->
    <div class="gradient-transition-faq-contact z-20 relative"></div>

    <!-- Contact Section -->
    <section id="contact" class="py-20 bg-white z-20 relative">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <h2 class="text-4xl font-bold text-center mb-12">Contact Us</h2>
        <form @submit.prevent="submitForm" class="max-w-lg mx-auto space-y-4">
          <div>
            <label for="name" class="block text-gray-700">Name</label>
            <input
              v-model="form.name"
              type="text"
              id="name"
              class="w-full p-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-600"
              required
            />
          </div>
          <div>
            <label for="email" class="block text-gray-700">Email</label>
            <input
              v-model="form.email"
              type="email"
              id="email"
              class="w-full p-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-600"
              required
            />
          </div>
          <div>
            <label for="message" class="block text-gray-700">Message</label>
            <textarea
              v-model="form.message"
              id="message"
              rows="5"
              class="w-full p-3 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-600"
              required
            ></textarea>
          </div>
          <button
            type="submit"
            class="bg-blue-600 text-white px-6 py-3 rounded-full w-full hover:bg-blue-700 transition duration-300"
          >
            Send Message
          </button>
        </form>
      </div>
    </section>

    <!-- Gradient Transition: Contact to Footer -->
    <div class="gradient-transition-contact-footer z-20 relative"></div>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-8 z-20 relative">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <p>© 2025 Hap Studios. All rights reserved.</p>
      </div>
    </footer>
  </div>
</template>

<script>
import emailjs from "emailjs-com";

export default {
  data() {
    return {
      sections: ["Home", "Pricing", "Hosting", "About", "FAQ", "Contact"],
      websitePlans: [
        {
          name: "Basic",
          pages: "1-3 Pages",
          price: "$295",
          features: [
            "Responsive Design",
            "SEO Optimization",
            "Contact Form",
            "Social Media Integration",
          ],
        },
        {
          name: "Pro",
          pages: "5-7 Pages",
          price: "$999",
          features: [
            "All Basic Features",
            "Custom Graphics",
            "Blog Setup",
            "Analytics Integration",
          ],
        },
        {
          name: "Elite",
          pages: "Webstores & Booking",
          price: "$1499",
          features: [
            "All Pro Features",
            "E-commerce Functionality",
            "Booking System",
            "Payment Integration",
          ],
        },
      ],
      hostingPlans: [
        {
          name: "Basic Hosting",
          price: "$49/month",
          features: [
            "Reliable Uptime",
            "SSL Certificate",
            "Basic Support",
            "No Edits",
          ],
        },
        {
          name: "Pro Hosting",
          price: "$99/month",
          features: [
            "All Basic Features",
            "Quarterly Edits",
            "Priority Support",
            "Enhanced Security",
          ],
        },
      ],
      faqs: [
        {
          question: "How long does it take to build a website?",
          answer:
            "Depending on the complexity, a basic website can take 2-4 weeks, while more advanced sites like e-commerce platforms may take 6-8 weeks.",
        },
        {
          question: "Do you offer ongoing maintenance?",
          answer:
            "Yes, our Pro Hosting plan includes quarterly edits, and we offer custom maintenance packages for additional updates.",
        },
        {
          question: "Can you help with SEO?",
          answer:
            "Absolutely! All our websites include basic SEO optimization, and we offer advanced SEO services upon request.",
        },
      ],
      form: {
        name: "",
        email: "",
        message: "",
      },
    };
  },
  mounted() {
    // Initialize EmailJS with your User ID
    emailjs.init("YOUR_USER_ID"); // Replace with your EmailJS User ID
  },
  methods: {
    scrollTo(section) {
      const element = document.getElementById(section);
      if (element) {
        window.scrollTo({
          top: element.offsetTop - 64,
          behavior: "smooth",
        });
      }
    },
    submitForm() {
      if (!this.form.name || !this.form.email || !this.form.message) {
        alert("Please fill in all fields.");
        return;
      }

      const templateParams = {
        name: this.form.name,
        email: this.form.email,
        message: this.form.message,
      };

      emailjs
        .send(
          "service_48df8j9", // Replace with your EmailJS Service ID
          "template_3encsi6", // Replace with your EmailJS Template ID
          templateParams
        )
        .then(
          (response) => {
            console.log("SUCCESS!", response.status, response.text);
            alert("Thank you for your message! We will get back to you soon.");
            this.form = { name: "", email: "", message: "" };
          },
          (error) => {
            console.log("FAILED...", error);
            alert("Failed to send message. Please try again later.");
          }
        );
    },
  },
};
</script>
