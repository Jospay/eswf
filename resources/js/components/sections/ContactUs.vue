<script setup lang="ts">
const contactData = {
    phone: ['+63 977 335 4714', '(02) 8373 2200'],

    email: 'contact@eswf.com',

    address: [
        '85 Dona Justina St. Cor. Dalton St. Filinvest II, Brgy. Batasan Hills Quezon City, Philippines',
        'Avenida De Venceslau De Morais, No, 218A, Macau Daily Building 16th floor, Macau',
    ],

    socials: [
        {
            name: 'Facebook',
            url: 'https://www.facebook.com/eswfofficial?mibextid=ZbWKwL',
            imagePath: '/assets/fb.png',
        },
        {
            name: 'Youtube',
            url: 'https://www.youtube.com/@esportsworldfederation',
            imagePath: '/assets/yt.png',
        },
        {
            name: 'Instagram',
            url: 'https://www.instagram.com/eswfofficial',
            imagePath: '/assets/ig.png',
        },
        {
            name: 'LinkedIn',
            url: 'https://www.linkedin.com/in/esports-world-federation-861927296/',
            imagePath: '/assets/in.png',
        },
        {
            name: 'Switch',
            url: 'https://www.twitch.tv/esportsworldfederation',
            imagePath: '/assets/tw.png',
        },
        {
            name: 'Twitter',
            url: 'https://x.com/ESWF11?t=lVc4OMHE_aNTimgdkfgkCA&s=07',
            imagePath: '/assets/x.png',
        },
        {
            name: 'Tiktok',
            url: 'https://www.tiktok.com/@esports.world.fed?is_from_webapp=1&sender_device=pc',
            imagePath: '/assets/tiktok.png',
        },
    ],
    meta:[
    {
        image: `/assets/metag.png`,
        title:`MetaSports Management Eco-System`,
        color:`#1BAF6B`
    },
    {
        image: `/assets/metab.png`,
        title:`MetaSports Diplomacy`,
        color:`#137DC1`
    },
    {
        image: `/assets/metay.png`,
        title:`Metasports Licensing`,
        color:`#FBD408  `
    },
    {
        image: `/assets/metagames.png`,
        title:`publisher Partners`,
        color:`black`
    },
    ]
};


</script>

<template>
    <section class="w-full overflow-hidden py-10 dark:bg-neutral-900">
        <div
            class="mb-10 flex w-full flex-col items-center justify-center px-4 text-center"
        >
            <h2
                class="text-2xl font-bold text-[#137DC1] sm:text-3xl md:text-4xl"
            >
                Contact Us
            </h2>
        </div>

        <div
            class="mx-auto flex max-w-6xl flex-col overflow-hidden rounded-2xl bg-white shadow-[0_0_20px_0_rgba(191,219,254,0.8)] dark:shadow-2lg  lg:flex-row dark:bg-gray-800"
        >
            <div class="flex w-full flex-col gap-2 p-4 lg:w-[55%] lg:p-10">
                <div class="flex flex-col">
                    <label class="text-sm font-bold text-[#137DC1]"
                        >Full Name</label
                    >
                    <input
                        type="text"
                        placeholder="Juan Dela Cruz"
                        class="rounded-lg border border-[#137DC1] bg-transparent px-4 py-2.5 text-gray-900 transition-all outline-none focus:ring-4 focus:ring-[#137DC1]/20 dark:text-white"
                    />
                </div>

                <div class="flex flex-col">
                    <label class="text-sm font-bold text-[#137DC1]"
                        >Organization / Company Name</label
                    >
                    <input
                        type="text"
                        placeholder="Your Company/Organization"
                        class="rounded-lg border border-[#137DC1] bg-transparent px-4 py-2.5 text-gray-900 transition-all outline-none focus:ring-4 focus:ring-[#137DC1]/20 dark:text-white"
                    />
                </div>

                <div class="flex flex-col">
                    <label class="text-sm font-bold text-[#137DC1]"
                        >Email Address</label
                    >
                    <input
                        type="email"
                        placeholder="john@example.com"
                        class="rounded-lg border border-[#137DC1] bg-transparent px-4 py-2.5 text-gray-900 transition-all outline-none focus:ring-4 focus:ring-[#137DC1]/20 dark:text-white"
                    />
                </div>

                <div class="flex flex-col gap-1.5">
                    <label class="text-sm font-bold text-[#137DC1]"
                        >Subject</label
                    >
                    <input
                        type="text"
                        placeholder="How can we help you?"
                        class="rounded-lg border border-[#137DC1] bg-transparent px-4 py-2.5 text-gray-900 transition-all outline-none focus:ring-4 focus:ring-[#137DC1]/20 dark:text-white"
                    />
                </div>

                <div class="flex flex-col gap-1.5">
                    <label class="text-sm font-bold text-[#137DC1]"
                        >Message</label
                    >
                    <textarea
                        rows="5"
                        placeholder="Write your message here..."
                        class="resize-none rounded-lg border border-[#137DC1] bg-transparent px-4 py-2.5 text-gray-900 transition-all outline-none focus:ring-4 focus:ring-[#137DC1]/20 dark:text-white"
                    ></textarea>
                </div>

                <div class="mt-2 flex justify-end">
                    <button
                        type="button"
                        class="inline-flex items-center justify-center rounded-lg bg-[#137DC1] px-10 py-3 text-base font-semibold text-white shadow-md transition-all duration-300 hover:-translate-y-1 hover:bg-[#4089f7]"
                    >
                        Submit
                    </button>
                </div>
            </div>

            <div
                class="flex w-full flex-col gap-1 bg-[#137DC1] p-4 text-white lg:w-[45%] lg:p-10"
            >
                <h3 class="text-center text-3xl font-bold text-white">
                    Contact Info
                </h3>

                <div class="flex flex-col gap-8">
                    <div
                        class="flex items-start gap-3 rounded-xl border border-amber-50 p-2 sm:gap-4 sm:p-1"
                    >
                        <div
                            class="flex h-10 w-10 shrink-0 items-center justify-center rounded-2xl border border-white bg-white p-1 shadow-sm sm:h-12 sm:w-12"
                        >
                            <svg
                                viewBox="0 0 24 24"
                                fill="none"
                                xmlns="http://www.w3.org/2000/svg"
                            >
                                <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
                                <g
                                    id="SVGRepo_tracerCarrier"
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                ></g>
                                <g id="SVGRepo_iconCarrier">
                                    <path
                                        d="M15.5562 14.5477L15.1007 15.0272C15.1007 15.0272 14.0181 16.167 11.0631 13.0559C8.10812 9.94484 9.1907 8.80507 9.1907 8.80507L9.47752 8.50311C10.1841 7.75924 10.2507 6.56497 9.63424 5.6931L8.37326 3.90961C7.61028 2.8305 6.13596 2.68795 5.26145 3.60864L3.69185 5.26114C3.25823 5.71766 2.96765 6.30945 3.00289 6.96594C3.09304 8.64546 3.81071 12.259 7.81536 16.4752C12.0621 20.9462 16.0468 21.1239 17.6763 20.9631C18.1917 20.9122 18.6399 20.6343 19.0011 20.254L20.4217 18.7584C21.3806 17.7489 21.1102 16.0182 19.8833 15.312L17.9728 14.2123C17.1672 13.7486 16.1858 13.8848 15.5562 14.5477Z"
                                        fill="#137DC1"
                                    ></path>
                                    <path
                                        d="M13.2595 1.87983C13.3257 1.47094 13.7122 1.19357 14.1211 1.25976C14.1464 1.26461 14.2279 1.27983 14.2705 1.28933C14.3559 1.30834 14.4749 1.33759 14.6233 1.38082C14.9201 1.46726 15.3347 1.60967 15.8323 1.8378C16.8286 2.29456 18.1544 3.09356 19.5302 4.46936C20.906 5.84516 21.705 7.17097 22.1617 8.16725C22.3899 8.66487 22.5323 9.07947 22.6187 9.37625C22.6619 9.52466 22.6912 9.64369 22.7102 9.72901C22.7197 9.77168 22.7267 9.80594 22.7315 9.83125L22.7373 9.86245C22.8034 10.2713 22.5286 10.6739 22.1197 10.7401C21.712 10.8061 21.3279 10.53 21.2601 10.1231C21.258 10.1121 21.2522 10.0828 21.2461 10.0551C21.2337 9.9997 21.2124 9.91188 21.1786 9.79572C21.1109 9.56339 20.9934 9.21806 20.7982 8.79238C20.4084 7.94207 19.7074 6.76789 18.4695 5.53002C17.2317 4.29216 16.0575 3.59117 15.2072 3.20134C14.7815 3.00618 14.4362 2.88865 14.2038 2.82097C14.0877 2.78714 13.9417 2.75363 13.8863 2.7413C13.4793 2.67347 13.1935 2.28755 13.2595 1.87983Z"
                                        fill="#137DC1"
                                    ></path>
                                    <path
                                        fill-rule="evenodd"
                                        clip-rule="evenodd"
                                        d="M13.4857 5.3293C13.5995 4.93102 14.0146 4.7004 14.4129 4.81419L14.2069 5.53534C14.4129 4.81419 14.4129 4.81419 14.4129 4.81419L14.4144 4.81461L14.4159 4.81505L14.4192 4.81602L14.427 4.81834L14.4468 4.8245C14.4618 4.82932 14.4807 4.8356 14.5031 4.84357C14.548 4.85951 14.6074 4.88217 14.6802 4.91337C14.8259 4.97581 15.0249 5.07223 15.2695 5.21694C15.7589 5.50662 16.4271 5.9878 17.2121 6.77277C17.9971 7.55775 18.4782 8.22593 18.7679 8.7154C18.9126 8.95991 19.009 9.15897 19.0715 9.30466C19.1027 9.37746 19.1254 9.43682 19.1413 9.48173C19.1493 9.50418 19.1555 9.52301 19.1604 9.53809L19.1665 9.55788L19.1688 9.56563L19.1698 9.56896L19.1702 9.5705C19.1702 9.5705 19.1707 9.57194 18.4495 9.77798L19.1707 9.57194C19.2845 9.97021 19.0538 10.3853 18.6556 10.4991C18.2607 10.6119 17.8492 10.3862 17.7313 9.99413L17.7276 9.98335C17.7223 9.96832 17.7113 9.93874 17.6928 9.89554C17.6558 9.8092 17.5887 9.66797 17.4771 9.47938C17.2541 9.10264 16.8514 8.53339 16.1514 7.83343C15.4515 7.13348 14.8822 6.73078 14.5055 6.50781C14.3169 6.39619 14.1757 6.32909 14.0893 6.29209C14.0461 6.27358 14.0165 6.26254 14.0015 6.25721L13.9907 6.25352C13.5987 6.13564 13.3729 5.72419 13.4857 5.3293Z"
                                        fill="#137DC1"
                                    ></path>
                                </g>
                            </svg>
                        </div>

                        <div class="flex flex-col justify-center gap-1 py-1">
                            <p
                                v-for="(num, index) in contactData.phone"
                                :key="index"
                                class="text-base font-medium text-white sm:text-lg"
                            >
                                {{ num }}
                            </p>
                        </div>
                    </div>

                    <div
                        class="flex items-start gap-4 rounded-xl border border-amber-50 p-1"
                    >
                        <div
                            class="flex h-12 w-12 shrink-0 items-center justify-center rounded-2xl border border-white bg-white p-2 shadow-sm"
                        >
                            <svg
                                fill="#137dc1"
                                viewBox="0 0 1920 1920"
                                xmlns="http://www.w3.org/2000/svg"
                                stroke="#137dc1"
                            >
                                <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
                                <g
                                    id="SVGRepo_tracerCarrier"
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                ></g>
                                <g id="SVGRepo_iconCarrier">
                                    <path
                                        d="M1920 428.266v1189.54l-464.16-580.146-88.203 70.585 468.679 585.904H83.684l468.679-585.904-88.202-70.585L0 1617.805V428.265l959.944 832.441L1920 428.266ZM1919.932 226v52.627l-959.943 832.44L.045 278.628V226h1919.887Z"
                                        fill-rule="evenodd"
                                    ></path>
                                </g>
                            </svg>
                        </div>
                        <div class="flex flex-col justify-center py-1">
                            <p class="text-lg font-medium text-white">
                                {{ contactData.email }}
                            </p>
                        </div>
                    </div>

                    <div
                        class="flex items-start gap-4 rounded-xl border border-amber-50 p-1"
                    >
                        <div
                            class="flex h-12 w-12 shrink-0 items-center justify-center rounded-2xl border border-white bg-white p-1 shadow-sm"
                        >
                            <svg
                                viewBox="0 0 16 16"
                                version="1.1"
                                xmlns="http://www.w3.org/2000/svg"
                                xmlns:xlink="http://www.w3.org/1999/xlink"
                                class="si-glyph si-glyph-pin-location-2"
                                fill="#000000"
                                stroke="#000000"
                            >
                                <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
                                <g
                                    id="SVGRepo_tracerCarrier"
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                ></g>
                                <g id="SVGRepo_iconCarrier">
                                    <title>Pin-location-2</title>
                                    <defs></defs>
                                    <g
                                        stroke="none"
                                        stroke-width="1"
                                        fill="none"
                                        fill-rule="evenodd"
                                    >
                                        <g
                                            transform="translate(2.000000, 0.000000)"
                                            fill="#137DC1"
                                        >
                                            <path
                                                d="M6,0.031 C3.283,0.031 1.08,2.15 1.08,4.764 C1.08,5.439 1.23,6.081 1.494,6.662 L6.084,13.983 L10.506,6.662 C10.771,6.081 10.918,5.438 10.918,4.764 C10.918,2.15 8.717,0.031 6,0.031 L6,0.031 Z M6,8.121 C4.295,8.121 2.915,6.734 2.915,5.023 C2.915,3.314 4.295,1.926 6,1.926 C7.703,1.926 9.086,3.314 9.086,5.023 C9.086,6.734 7.703,8.121 6,8.121 L6,8.121 Z M7.977,4.983 C7.977,6.08 7.091,6.968 5.999,6.968 C4.908,6.968 4.022,6.079 4.022,4.983 C4.022,3.888 4.908,3 5.999,3 C7.091,3 7.977,3.889 7.977,4.983 L7.977,4.983 Z"
                                                class="si-glyph-fill"
                                            ></path>
                                            <path
                                                d="M3.29899999,11.8232422 C1.58199999,12.1872422 0.869751004,12.6649999 0.869751004,13.2019999 C0.869751004,13.9709999 2.7,15.031 5.985,15.031 C9.27,15.031 11.1014406,13.9709999 11.1014406,13.2019999 C11.1014406,12.6669999 10.393,12.2032422 8.70000002,11.8232422 L8.7,11.003 C10.565,11.369 11.954,12.104 11.954,13.202 C11.954,14.786 8.87799986,15.9729004 5.98499986,15.9729004 C3.09199986,15.9729004 0.0160000001,14.786 0.0160000001,13.202 C0.0160000001,12.102 1.414,11.353 3.289,11 L3.29899999,11.8232422 Z"
                                                class="si-glyph-fill"
                                            ></path>
                                        </g>
                                    </g>
                                </g>
                            </svg>
                        </div>

                        <div class="flex flex-col justify-center gap-4 py-1">
                            <div class="flex flex-col gap-4">
                                <p
                                    v-for="(addr, index) in contactData.address"
                                    :key="index"
                                    class="text-base sm:text-lg font-medium text-white">
                                    {{ addr }}
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
<div class="mt-auto flex flex-col gap-2">
    <h4 class="text-xl font-bold text-white">Follow Us:</h4>

    <div class="flex items-center gap-2 sm:gap-3">
        <a
            v-for="social in contactData.socials"
            :key="social.name"
            :href="social.url"
            target="_blank"
            rel="noopener noreferrer"
            class="flex h-12 w-12 shrink-0 items-center justify-center rounded-xl bg-white shadow-md transition-all duration-300 hover:-translate-y-1 hover:shadow-lg"
        >
            <img
                :src="social.imagePath"
                :alt="social.name"
                class="h-8 w-8 object-contain"
            />
        </a>
    </div>
</div>
            </div>
        </div>
        
        <div class="mx-auto mt-10 flex max-w-6xl flex-col px-4 sm:mt-16 sm:px-8">
            <div class="grid grid-cols-1 gap-6 sm:grid-cols-2 lg:gap-8">
                <div
                    v-for="(item, index) in contactData.meta"
                    :key="index"
                    class="flex items-center gap-6 rounded-xl bg-white p-6 transition-transform duration-300 hover:-translate-y-1 dark:bg-gray-800"
                    :style="{ boxShadow: `0px 4px 12px -2px ${item.color}` }"
                >
                    <img
                        :src="item.image"
                        :alt="item.title"
                        class="h-14 w-14 shrink-0 object-contain sm:h-16 sm:w-16"
                    />
                    <h4
                        class="text-lg font-bold leading-snug sm:text-xl"
                        :style="{ color: item.color }"
                    >
                        {{ item.title }}
                    </h4>
                </div>
            </div>
        </div>
    </section>
</template>
