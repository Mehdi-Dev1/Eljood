<template>

  <!-- Section Header -->
  <header class="bg-black text-white py-8">
    <div class="container mx-auto flex justify-between items-center px-6">
      <div class="text-3xl font-bold">El Jood</div>
      <!-- Hamburger Icon -->
      <button
        @click="toggleMenu"
        class="sm:hidden text-white focus:outline-none"
        aria-label="Toggle Menu"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-8 w-8"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16"
          />
        </svg>
      </button>
      <!-- Desktop Navigation -->
      <nav class="hidden sm:flex space-x-8">
        <a href="#menu" class="hover:text-yellow-500 transition">Menu</a>
        <a href="#about" class="hover:text-yellow-500 transition">À propos</a>
        <a href="#location" class="hover:text-yellow-500 transition">Localisation</a>
        <a href="#contact" class="hover:text-yellow-500 transition">Contact</a>
      </nav>
    </div>
  </header>

  <!-- Mobile Menu (Sliding Navigation) -->
  <div
    :class="{'translate-x-0': menuOpen, '-translate-x-full': !menuOpen}"
    class="fixed top-0 left-0 h-full w-2/3 bg-black text-white transform transition-transform duration-300 z-50 sm:hidden"
  >
    <div class="p-6">
      <button
        @click="toggleMenu"
        class="text-white focus:outline-none"
        aria-label="Close Menu"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M6 18L18 6M6 6l12 12"
          />
        </svg>
      </button>
      <ul class="mt-8 space-y-6">
        <li><a href="#menu" @click="toggleMenu" class="block text-lg hover:text-yellow-500 transition">Menu</a></li>
        <li><a href="#about" @click="toggleMenu" class="block text-lg hover:text-yellow-500 transition">À propos</a></li>
        <li><a href="#location" @click="toggleMenu" class="block text-lg hover:text-yellow-500 transition">Localisation</a></li>
        <li><a href="#contact" @click="toggleMenu" class="block text-lg hover:text-yellow-500 transition">Contact</a></li>
      </ul>
    </div>
  </div>

  <!-- Overlay for Mobile Menu -->
  <div
    v-if="menuOpen"
    @click="toggleMenu"
    class="fixed inset-0 bg-black bg-opacity-50 z-40 sm:hidden"
  ></div>

  <!-- Hero Section -->
  <section class="relative h-96 flex justify-center items-center text-center text-white">
    <img 
      src="../assets/banner.jpg" 
      alt="Bannière Jood" 
      class="absolute inset-0 h-full w-full object-cover" 
    />
    <div class="absolute inset-0 bg-black opacity-50"></div>
    <div class="relative">
      <h1 class="text-4xl font-bold mb-4">Les Meilleurs Kebab, Pizzas, Burgers & Sandwiches !</h1>
      <p class="text-xl mb-6">Chez El Jood, on vous régale avec des plats savoureux et faits maison</p>
      <a href="#menu" class="bg-yellow-500 text-black py-2 px-6 rounded-full text-lg font-semibold hover:bg-yellow-400 transition">Voir le Menu</a>
    </div>
  </section>

  <!-- Menu Section -->
  <section id="menu" class="py-16 bg-white">
    <div class="container mx-auto text-center">
      <h2 class="text-3xl font-bold mb-8">Notre Menu</h2>
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-12">
        <div class="bg-gray-200 p-6 rounded-lg shadow-lg">
          <h3 class="text-xl font-semibold mb-2">Kebab</h3>
          <p class="text-gray-700 mb-4">Délicieux kebab avec des sauces maison</p>
          <span class="text-yellow-500 font-bold">€6.50</span>
        </div>
        <div class="bg-gray-200 p-6 rounded-lg shadow-lg">
          <h3 class="text-xl font-semibold mb-2">Pizza</h3>
          <p class="text-gray-700 mb-4">Pizzas artisanales à base de produits frais</p>
          <span class="text-yellow-500 font-bold">€8.00</span>
        </div>
        <div class="bg-gray-200 p-6 rounded-lg shadow-lg">
          <h3 class="text-xl font-semibold mb-2">Burger</h3>
          <p class="text-gray-700 mb-4">Burgers gourmands avec viande de qualité</p>
          <span class="text-yellow-500 font-bold">€7.00</span>
        </div>
        <div class="bg-gray-200 p-6 rounded-lg shadow-lg">
          <h3 class="text-xl font-semibold mb-2">Sandwich</h3>
          <p class="text-gray-700 mb-4">Sandwichs chauds et savoureux</p>
          <span class="text-yellow-500 font-bold">€5.50</span>
        </div>
      </div>
    </div>
  </section>

  <!-- Ordering Section -->
  <section id="order" class="py-16 bg-gray-100">
    <div class="container mx-auto text-center">
      <h2 class="text-3xl font-bold mb-8">Commandez en ligne</h2>
      <p class="text-lg mb-6">Profitez de nos délicieux plats chez vous grâce à nos partenaires de livraison !</p>
      <div class="flex justify-center items-center space-x-8">
        <a href="https://www.ubereats.com/fr/store/eljood/xIBEbOnySPSBor6zD3Wgfw?mod=storeDeliveryTime&modctx=%257B%2522entryPoint%2522%253A%2522store-auto-surface%2522%252C%2522encodedStoreUuid%2522%253A%2522xIBEbOnySPSBor6zD3Wgfw%2522%257D&pl=JTdCJTIyYWRkcmVzcyUyMiUzQSUyMjM4JTIwUnVlJTIwVGhpZXJzJTIyJTJDJTIycmVmZXJlbmNlJTIyJTNBJTIyQ2hJSlhZS0FMbzRvdzBjUll5eXR4TnVXSV84JTIyJTJDJTIycmVmZXJlbmNlVHlwZSUyMiUzQSUyMmdvb2dsZV9wbGFjZXMlMjIlMkMlMjJsYXRpdHVkZSUyMiUzQTUwLjY4NzM0NTQlMkMlMjJsb25naXR1ZGUlMjIlM0EzLjE4NjU2MTMlN0Q%3D&ps=1" target="_blank" class="hover:opacity-80 transition">
          <img src="../assets/ubereat.png" alt="Uber Eats" class="h-16">
        </a>
        <a href="https://deliveroo.fr/fr/menu/lille/roubaix-sud/eljood" target="_blank" class="hover:opacity-80 transition">
          <img src="../assets/delivero.png" alt="Deliveroo" class="h-16">
        </a>
      </div>
    </div>
  </section>

  <!-- About Section -->
  <section id="about" class="py-16 bg-gray-200">
    <div class="container mx-auto text-center">
      <h2 class="text-3xl font-bold mb-8">À propos de El Jood</h2>
      <p class="text-lg mb-4 max-w-3xl mx-auto">Chez El Jood, nous mettons un point d'honneur à vous offrir des repas de qualité, préparés avec des ingrédients frais et locaux. Notre équipe passionnée vous prépare des plats savoureux qui sauront ravir vos papilles à chaque bouchée.</p>
      <p class="text-lg mt-4">Visitez-nous à notre adresse : <a href="#location" class="text-yellow-500 hover:underline">144B Rue de Lannoy, 59100 Roubaix</a>.</p>
    </div>
  </section>

  <!-- Location Section -->
  <section id="location" class="py-16 bg-white">
    <div class="container mx-auto text-center">
      <h2 class="text-3xl font-bold mb-8">Notre Localisation</h2>
      <p class="text-lg mb-4">Vous pouvez nous retrouver à l'adresse suivante :</p>
      <p class="text-lg font-semibold mb-6">144B Rue de Lannoy, 59100 Roubaix</p>
      <div class="relative overflow-hidden rounded-lg shadow-lg h-96">
        <iframe
  class="absolute inset-0 w-full h-full"
  src="https://www.google.com/maps?q=144B+Rue+de+Lannoy,+59100+Roubaix&output=embed"
  allowfullscreen
  loading="lazy"
></iframe>

      </div>
    </div>
  </section>

  <!-- Contact Section -->
  <section id="contact" class="py-16 bg-black text-white">
    <div class="container mx-auto text-center">
      <h2 class="text-3xl font-bold mb-8">Contactez-nous</h2>
      <p class="text-lg mb-4">Besoin de plus d'informations ? N'hésitez pas à nous contacter !</p>
      <p class="text-lg mb-4">Téléphone : <strong>09 84 25 94 20</strong></p>
      <p class="text-lg mb-4">Email : <strong>contact@jood.fr</strong></p>
    </div>
  </section>

  <!-- Footer -->
  <footer class="bg-gray-800 text-white py-8">
    <div class="container mx-auto text-center">
      <p>&copy; 2024 El Jood - Tous droits réservés.</p>
    </div>
  </footer>

</template>

<script>
export default {
name: 'App',
data() {
  return {
    menuOpen: false, // État pour afficher/masquer le menu burger
  };
},
methods: {
  toggleMenu() {
    this.menuOpen = !this.menuOpen;
  },
},
};
</script>

<style scoped>
/* Mobile Menu Animation */
.fixed {
box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}
</style>
