<template>
  <nav class="bg-custom-blues top-0 absolute z-50 w-full">
    <div class="container px-4 mx-auto flex flex-wrap items-center justify-center py-3">
      <div class="w-full md:w-1/4 flex justify-center">
        <!-- Logo Section -->
        <button>
          <img src="https://i.ibb.co/PQMcZ8R/ocean-air-flow-logos-transparent.png" alt="ocean-air-flow-logos-transparent" border="0" width="200" height="200">
        </button>
      </div>
      <div class="w-full md:w-3/4 flex justify-end items-center">
        <!-- Call Us Button -->
        <a class="text-blue-500 text-lg font-bold mr-6" href="tel:888-888-8888">Call us today! 888-888-8888</a>
      </div>
    </div>

    <div class="container px-4 mx-auto flex flex-wrap items-center justify-center py-3">
      <div class="w-full relative flex justify-between lg:w-auto lg:static lg:block lg:justify-start">
        <button class="cursor-pointer text-xl leading-none px-3 py-1 border border-solid border-transparent rounded bg-transparent block lg:hidden outline-none focus:outline-none" type="button" @click="toggleNavbar()">
          <i class="text-blue-500 fas fa-bars"></i>
        </button>
      </div>
      <div class="lg:flex flex-grow items-center bg-custom-blues lg:bg-transparent lg:shadow-none" :class="{'hidden': !showMenu, 'block': showMenu}">
        <ul class="flex flex-col lg:flex-row list-none mr-auto">
          <li class="flex items-center">
            <a class="lg:hover:text-blue-500 text-blue-500  px-3 py-4 lg:py-2 flex items-center text-xs uppercase font-bold" href="#home">Home</a>
          </li>
          <li class="relative group flex items-center">
            <a class="lg:hover:text-blue-500 text-blue-500  px-3 py-4 lg:py-2 flex items-center text-xs uppercase font-bold cursor-pointer" @click="toggleHeatingDropdown">Heating</a>
            <ul @mouseleave="closeDropdowns" v-if="showHeatingDropdown" class="absolute left-0 mt-2 bg-white text-gray-800 border border-gray-300 py-2 rounded-lg shadow-lg">
              <li><a class="block px-4 py-2 hover:bg-gray-200" href="#heating-option1">Heating Option 1</a></li>
              <li><a class="block px-4 py-2 hover:bg-gray-200" href="#heating-option2">Heating Option 2</a></li>
            </ul>
          </li>
          <li class="relative group flex items-center">
            <a class="lg:hover:text-blue-500 text-blue-500  px-3 py-4 lg:py-2 flex items-center text-xs uppercase font-bold cursor-pointer" @click="toggleACDropdown">Air Conditioning</a>
            <ul @mouseleave="closeDropdowns" v-if="showACDropdown" class="absolute left-0 mt-2 bg-white text-gray-800 border border-gray-300 py-2 rounded-lg shadow-lg">
              <li><a class="block px-4 py-2 hover:bg-gray-200" href="#ac-option1">AC Option 1</a></li>
              <li><a class="block px-4 py-2 hover:bg-gray-200" href="#ac-option2">AC Option 2</a></li>
            </ul>
          </li>
          <li class="flex items-center">
            <a class="lg:hover:text-blue-500 text-blue-500  px-3 py-4 lg:py-2 flex items-center text-xs uppercase font-bold" href="#location">Location</a>
          </li>
          <li class="flex items-center">
            <a class="lg:hover:text-blue-500 text-blue-500 px-3 py-4 lg:py-2 flex items-center text-xs uppercase font-bold" href="#contact-us">Contact Us</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      showMenu: false,
      showHeatingDropdown: false,
      showACDropdown: false
    };
  },
  methods: {
    toggleNavbar() {
      this.showMenu = !this.showMenu;
    },
    closeDropdowns() {
      this.showHeatingDropdown = false;
      this.showACDropdown = false;
    },
    toggleHeatingDropdown() {
      this.showHeatingDropdown = !this.showHeatingDropdown;
      this.showACDropdown = false;
    },
    toggleACDropdown() {
      this.showACDropdown = !this.showACDropdown;
      this.showHeatingDropdown = false;
    }
  }
};
</script>

<style>
.bg-custom-blues {
  background-color: white;
}
.bg-custom-blue {
  background-color: #5B4BE3;
}

.text-blue-500 {
  color: #5B4BE3;
}

.text-blue-500:hover {
  color: #786EF0; /* A different but similar color for hover */
}

.flex-wrap {
  justify-content: center;
}
</style>
