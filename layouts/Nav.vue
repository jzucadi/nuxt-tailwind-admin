<template>
  <nav id="header" class="bg-white fixed w-full z-10 top-0 shadow-md">
    <div
      class="w-full container mx-auto flex flex-wrap items-center mt-0 pt-3 pb-3 md:pb-0"
    >
      <div class="w-1/2 pl-2 md:pl-0">
        <a
          class="text-gray-900 text-base xl:text-xl no-underline hover:no-underline font-bold"
          href="#"
        >
          <i class="fas fa-tint text-blue-600 pr-0"></i> Ocean Trust
        </a>
      </div>
      <div class="w-1/2 pr-0">
        <div class="flex relative inline-block float-right">
          <div class="relative text-sm">
            <button
              id="userButton"
              class="flex items-center focus:outline-none mr-3"
              style="position: relative;top: 15px;z-index: 999;"
            >
              <span class="hidden md:inline-block">Welcome, John </span>
              <svg
                class="pl-2 h-2"
                version="1.1"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 129 129"
                xmlns:xlink="http://www.w3.org/1999/xlink"
                enable-background="new 0 0 129 129"
              >
                <g>
                  <path
                    d="m121.3,34.6c-1.6-1.6-4.2-1.6-5.8,0l-51,51.1-51.1-51.1c-1.6-1.6-4.2-1.6-5.8,0-1.6,1.6-1.6,4.2 0,5.8l53.9,53.9c0.8,0.8 1.8,1.2 2.9,1.2 1,0 2.1-0.4 2.9-1.2l53.9-53.9c1.7-1.6 1.7-4.2 0.1-5.8z"
                  />
                </g>
              </svg>
            </button>
            <div
              id="userMenu"
              class="bg-white rounded shadow-md mt-2 absolute mt-12 top-0 right-0 min-w-full overflow-auto z-30 invisible"
            >
              <ul class="list-reset">
                <li>
                  <a
                    href="#"
                    class="px-4 py-2 block text-gray-900 hover:bg-gray-400 no-underline hover:no-underline"
                    >My account</a
                  >
                </li>
                <li>
                  <a
                    href="#"
                    class="px-4 py-2 block text-gray-900 hover:bg-gray-400 no-underline hover:no-underline"
                    >Notifications</a
                  >
                </li>
                <li>
                  <a
                    href="#"
                    class="px-4 py-2 block text-gray-900 hover:bg-gray-400 no-underline hover:no-underline"
                    >Settings</a
                  >
                </li>
                <li><hr class="border-t mx-2 border-gray-400" /></li>
                <li>
                  <a
                    href="#"
                    class="px-4 py-2 block text-gray-900 hover:bg-gray-400 no-underline hover:no-underline"
                    >Logout</a
                  >
                </li>
              </ul>
            </div>
          </div>

          <div class="block lg:hidden pr-4">
            <button
              id="nav-toggle"
              class="flex items-center px-3 py-2 border rounded text-gray-500 border-gray-600 hover:text-gray-900 hover:border-teal-500 appearance-none focus:outline-none"
            >
              <svg
                class="fill-current h-3 w-3"
                viewBox="0 0 20 20"
                xmlns="http://www.w3.org/2000/svg"
              >
                <title>Menu</title>
                <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
              </svg>
            </button>
          </div>
        </div>
      </div>

      <div
        id="nav-content"
        class="w-full flex-grow lg:flex lg:items-center lg:w-auto hidden lg:block mt-2 lg:mt-0 bg-white z-20"
      >
        <ul class="list-reset lg:flex flex-1 items-center px-4 md:px-0">
          <li class="mr-6 my-2 md:my-0">
            <a
              href="#"
              class="block py-1 md:py-3 pl-1 align-middle text-blue-600 no-underline hover:text-gray-900 border-b-2 border-blue-300 hover:border-blue-400"
            >
              <i class="fas fa-tachometer-alt fa-fw mr-3 text-blue-400"></i
              ><span class="pb-1 md:pb-0 text-sm">Dashboard</span>
            </a>
          </li>
          <li class="mr-6 my-2 md:my-0">
            <a
              href="#"
              class="block py-1 md:py-3 pl-1 align-middle text-gray-500 no-underline hover:text-gray-900 border-b-2 border-white hover:border-blue-400"
            >
              <i class="fas fa-tasks fa-fw mr-3"></i
              ><span class="pb-1 md:pb-0 text-sm">Tasks</span>
            </a>
          </li>
          <li class="mr-6 my-2 md:my-0">
            <a
              href="#"
              class="block py-1 md:py-3 pl-1 align-middle text-gray-500 no-underline hover:text-gray-900 border-b-2 border-white hover:border-blue-400"
            >
              <i class="fa fa-file-contract fa-fw mr-3"></i
              ><span class="pb-1 md:pb-0 text-sm">Documents</span>
            </a>
          </li>
          <li class="mr-6 my-2 md:my-0">
            <a
              href="#"
              class="block py-1 md:py-3 pl-1 align-middle text-gray-500 no-underline hover:text-gray-900 border-b-2 border-white hover:border-blue-100"
            >
              <i class="fas fa-users fa-fw mr-3"></i
              ><span class="pb-1 md:pb-0 text-sm">Users</span>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  mounted() {
    const userMenuDiv = document.getElementById('userMenu');
    const userMenu = document.getElementById('userButton');

    const navMenuDiv = document.getElementById('nav-content');
    const navMenu = document.getElementById('nav-toggle');

    document.onclick = check;

    function check(e) {
      const target = (e && e.target) || (event && event.srcElement);

      // User Menu
      if (!checkParent(target, userMenuDiv)) {
        // click NOT on the menu
        if (checkParent(target, userMenu)) {
          // click on the link
          if (userMenuDiv.classList.contains('invisible')) {
            userMenuDiv.classList.remove('invisible');
          } else {
            userMenuDiv.classList.add('invisible');
          }
        } else {
          // click both outside link and outside menu, hide menu
          userMenuDiv.classList.add('invisible');
        }
      }

      // Nav Menu
      if (!checkParent(target, navMenuDiv)) {
        // click NOT on the menu
        if (checkParent(target, navMenu)) {
          // click on the link
          if (navMenuDiv.classList.contains('hidden')) {
            navMenuDiv.classList.remove('hidden');
          } else {
            navMenuDiv.classList.add('hidden');
          }
        } else {
          // click both outside link and outside menu, hide menu
          navMenuDiv.classList.add('hidden');
        }
      }
    }

    function checkParent(t, elm) {
      while (t.parentNode) {
        if (t === elm) {
          return true;
        }
        t = t.parentNode;
      }
      return false;
    }
  }
};
</script>
