<script setup>
import TheWelcome from '../components/TheWelcome.vue'
</script>

<template>
  <main>
    <!-- Hero Section -->
    <header class="bg-cover bg-center h-64 flex items-center text-white">
      <div class="container mx-auto text-center">
        <h1 class="text-4xl font-bold mb-2">Welcome to our about page</h1>
        <p class="text-lg text-blue-400">We bring joy to the viewers</p>
      </div>
    </header>

    <!-- Company Information Section -->
    <section class="container mx-auto my-8 p-8 bg-white shadow-lg rounded-lg">
      <h2 class="text-3xl font-bold mb-4">About Us</h2>
      <p class="text-lg mb-4">
        Sambíoinn is a leading entertainment company dedicated to creating and delivering exceptional film and
        television content. With a passion for storytelling, we aim to captivate audiences worldwide through
        compelling narratives and breathtaking visuals.
      </p>
      <p class="text-lg mb-4">
        Our journey began in 2023, driven by the vision of <span class="text-blue-400">Jakub Sienkiewicz</span> and <span class="text-blue-400">Agata Hirsz</span>. Since then, we have evolved into a dynamic
        force in the industry, producing award-winning films and engaging television series.
      </p>
      <p class="text-lg mb-4">
        At Sambioinn, we believe in the power of cinema to inspire, entertain, and provoke thought. Our commitment
        to quality and creativity sets us apart, and we continue to push boundaries in storytelling and filmmaking.
      </p>
    </section>

    <!-- Founders Section -->
    <section class="container mx-auto my-8 p-8 bg-gray-100 shadow-lg rounded-lg">
      <h2 class="text-3xl font-bold mb-4">Founders</h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <!-- Founder 1 -->
        <div class="bg-white p-4 rounded-lg shadow-md">
          <img src="https://images.wsj.net/im-887980?width=700&height=466" alt="Founder 1" class="w-full h-48 object-cover mb-4 rounded-lg">
          <h3 class="text-xl font-bold mb-2">Jakub Sienkiewicz</h3>
          <p class="text-gray-700">Founder & Lead-Developer</p>
        </div>

        <!-- Founder 2 -->
        <div class="bg-white p-4 rounded-lg shadow-md">
          <img src="https://t4.ftcdn.net/jpg/04/70/29/97/360_F_470299797_UD0eoVMMSUbHCcNJCdv2t8B2g1GVqYgs.jpg" alt="Founder 2" class="w-full h-48 object-cover mb-4 rounded-lg">
          <h3 class="text-xl font-bold mb-2">Agata Hirsz</h3>
          <p class="text-gray-700">Co-founder & Idea Manager</p>
        </div>

        <!-- Add more founders as needed -->
      </div>
    </section>

    <!-- Contact Section -->
    <section class="container mx-auto my-8 p-8 bg-white shadow-lg rounded-lg">
      <h2 class="text-3xl font-bold mb-4">Contact Us</h2>
      <p class="text-lg mb-4">
        We'd love to hear from you! Whether you have inquiries about our projects, collaborations, or just want to
        share your thoughts, feel free to reach out.
      </p>
      <p class="text-lg mb-4">
        Business inquires: <a href="mailto:info@moviecompany.com" class="text-blue-500">info@moviecompany.com</a>
      </p>
      <p class="text-lg mb-4">
        Phone: +354891891
      </p>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white p-4 text-center">
      <div class="container mx-auto">
        <p>&copy; 2023 Movie Company. All rights reserved.</p>
      </div>
    </footer>
  </main>
</template>
