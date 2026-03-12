<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';

const licenses = {
    images: [
        {
            url: 'https://eswf.games/wp-content/uploads/2023/11/oceania-722x1024.png',
            title: 'Oceania Inc. PERMIT',
        },
        {
            url: 'https://eswf.games/wp-content/uploads/2023/09/image-20-1024x423.png',
            title: 'Europe Permit',
        },
        {
            url: 'https://eswf.games/wp-content/uploads/2023/09/372030770_2246637015726283_1267984415005137516_n-648x1024.jpg',
            title: 'Africa Permit',
        },
    ],
    imageAlt: 'GAB Courtesy Visit',
    title: ['ESWF Pan America Permit', 'MetaGames Certificate'],
    license: 'Licenses',
    paragraphs: [
        'One of the roles of ESWF is to supervise, support and monitor the organization of the MetaGames; ensure that they run smoothly; and to make sure that the rules of the MetaGames Charter and the MetaGames Host Contract are respected.',
        'Januray 17, 2023',
    ],
    download: {
        link: [
            '/assets/ESWF-PanAm-Amendment-Modification-1.pdf',
            '/assets/META-GAMES_41_PH_Certificate-of-registration_B-2023-135331-1-1.pdf',
        ],
        label: 'Download Press Release',
        filename: [
            'ESWF-PanAm-Amendment-Modification.pdf',
            'META-GAMES-Certificate-of-Registration.pdf',
        ],
    },
    linkUrl:
        'https://www.facebook.com/100064530678864/posts/1029283105899369/?rdid=dcw7hOTuo40g8ExK#',
    linkText: 'Visit Website',
};

const article = {
    title: `The Esports World Federation (ESWF) Collaborates with GAB Chairman Atty. Richard S. Clarin to Propel Esports in the Philippines`,
    paragraphs: [
        `The Esports World Federation (ESWF), the pioneering internationally-oriented esports federation in the Philippines, recently paid a courtesy visit to GAB Chairman Atty. Richard S. Clarin, marking the beginning of a strategic partnership between the two organizations.
        As the governing body for all MetaSports in the MetaGames, the ESWF holds a significant position in the global esports landscape. Recognizing the immense potential and growing prominence of esports, the ESWF aims to forge a close alliance with GAB to position the Philippines as a leading hub for esports and elevate its status on the international stage.
        During the visit, fruitful discussions were held between the ESWF delegation and GAB Chairman Atty. Richard S. Clarin, highlighting the shared commitment to advancing the esports industry in the Philippines. Both parties expressed their enthusiasm for collaborative initiatives that will propel the country’s esports ecosystem to new heights.
        As the GAB and the ESWF embark on this impactful collaboration, the stage is set for a vibrant future for esports in the country. Stay tuned for exciting developments and initiatives that will shape the country’s esports landscape.`,
    ],
    images: [
        '/assets/collab1.jpg',
        '/assets/collab2.jpg',
        '/assets/collab3.jpg',
        '/assets/collab4.jpg',
    ],
    actionLink:
        'https://www.facebook.com/story.php?story_fbid=pfbid02qvnMda5ABn27Q6zFPF8yjbZgqknS4DqkEiBEn9aKL1gKYxdDCzZ7yo5pDTQ3mNH8l&id=100064530678864&mibextid=CDWPTG&_rdr',
    actionText: 'Visit Website',
};

const ewfLeader = {
    title: `Esports World Federation leaders touch base with PSC`,
    paragraphs: [
        'MANILA, Philippines – Officials and representatives of the Esports World Federation and General Association of World Sports Federations Macau China paid a courtesy call to Philippine Sports Commission (PSC) Chairman Richard Bachmann on Monday.',
        'In the photo (from left) are PSC Commissioner Walter Torres; Esports World Federation Chairman and Asian Television content Corporation CEO Engr. Reynaldo Sanchez; former Pagcor Gaming Department head Reynaldo De Guzman; General Association of World Sports Federations Macau China Chairman and President World Sports University  Dr. Che Kuong Hon and Esports World Federation Founder and President Arniel Gutierrez.',
        'PSC Bldg October 16, 2023',
    ],
    image: '/assets/psc.jpg',
    imageAlt: 'Philippine Sports Commission',
    links: [
        {
            text: 'Philstar.com',
            url: 'https://www.philstar.com/sports/2023/10/17/2304502/esports-world-federation-leaders-touch-base-psc?fbclid=IwAR0eZWgKkZmJ5uZSgSXauKJmoZ3gzV8AeFth36AX5PpqwfhwjVlMmCmCCPI',
            bgColor: 'bg-[#137DC1]',
            hoverColor: 'hover:bg-[#4089f7]',
            textColor: 'text-white',
        },
        {
            text: 'Metropoler.net',
            url: 'https://www.philstar.com/sports/2023/10/17/2304502/esports-world-federation-leaders-touch-base-psc?fbclid=IwAR0eZWgKkZmJ5uZSgSXauKJmoZ3gzV8AeFth36AX5PpqwfhwjVlMmCmCCPI',
            bgColor: 'bg-[#FBD408]',
            hoverColor: 'hover:bg-[#e5c107]',
            textColor: 'text-gray-800',
        },
    ],
};

const pdrciEsports = {
    title: `MOA signing Philippine Dispute Resolution Center and Esports World Federation`,
    paragraphs: [
        'PDRCI and Esports World Federation (ESWF), the umbrella organization of international organizations in electronic and digital sports and other game genres across the world, entered into a partnership to adopt and implement an alternative dispute resolution (ADR) policy to ensure speedy and cost-effective settlement of MetaSports-related disputes.',
        'PDRCI President Atty. Roberto N. Dio and ESWF Founder and President Mr. Arniel Gutierrez signed the agreement which was witnessed by ESWF Trustee and Vice Chair of the Game Development Commission Mr. Ranulf Goss, PDRCI Vice Chair Atty. Edmund L. Tan, and members of the PDRCI Sports Arbitration Committee (SAC): PDRCI Trustee and SAC Chair Atty. CHARLIE HO, PDRCI Executive Director and Deputy Secretary General Atty. Arleo Magtibay, Jr., PDRCI Trustee Atty. Joenar Pueblo, PDRCI Asst. Executive Director Atty. Alejandro P. Gaston Jr., Philippine Sports Commission (PSC) Deputy Executive Director Atty. Guillermo Iroy, and PSC Legal Affairs Head Atty. Michelle Labajanan.',
        'September 2023',
    ],
    image: '/assets/psc.jpg',
    imageAlt: 'Philippine Sports Commission',
    links: [
        {
            text: 'Linkedin.com',
            url: 'https://www.linkedin.com/posts/pdrci_pdrci-leadingtheway-philippineadr-activity-7102574394287296512-5YMD',
            bgColor: 'bg-[#137DC1]',
            hoverColor: 'hover:bg-[#4089f7]',
            textColor: 'text-white',
        },
    ],
    carouselItems: [
        '/assets/moa.jpg',
        '/assets/moa1.jpg',
        '/assets/moa2.jpg',
        '/assets/moa3.jpg',
    ],
};

const currentIndex = ref(0);
let intervalId: ReturnType<typeof setInterval>;

const getPosClass = (i: number) => {
    const total = pdrciEsports.carouselItems.length;
    const current = currentIndex.value;
    const left = (current - 1 + total) % total;
    const right = (current + 1) % total;

    if (i === current) {
        return 'left-0 w-full h-[350px] md:left-1/4 md:w-1/2 md:h-[480px] z-20 opacity-100';
    }
    if (i === left) {
        return 'left-0 w-0 h-[350px] opacity-0 md:w-1/4 md:h-[300px] md:opacity-100 z-10';
    }
    if (i === right) {
        return 'left-full md:left-[75%] w-0 h-[350px] opacity-0 md:w-1/4 md:h-[300px] md:opacity-100 z-10';
    }
    return 'left-1/2 w-0 h-[350px] opacity-0 z-0';
};

const nextSlide = () => {
    currentIndex.value =
        (currentIndex.value + 1) % pdrciEsports.carouselItems.length;
};

onMounted(() => {
    intervalId = setInterval(nextSlide, 3500);
});

onUnmounted(() => {
    clearInterval(intervalId);
});

const forceDownload = async (imgUrl: string, index: number) => {
    try {
        // Fetch the image data
        const response = await fetch(imgUrl);
        const blob = await response.blob();

        // Create a temporary local URL for the downloaded data
        const blobUrl = window.URL.createObjectURL(blob);

        // Create a hidden temporary link and click it
        const link = document.createElement('a');
        link.href = blobUrl;

        // Try to get the original filename, or set a default
        const originalFilename =
            imgUrl.split('/').pop() || `eswf-license-${index + 1}.png`;
        link.download = originalFilename;

        document.body.appendChild(link);
        link.click();

        // Clean up
        document.body.removeChild(link);
        window.URL.revokeObjectURL(blobUrl);
    } catch (error) {
        console.error('Download failed, opening in new tab instead:', error);
        // Fallback: just open it in a new tab if the fetch fails
        window.open(imgUrl, '_blank');
    }
};
</script>

<template>
    <section class="w-full overflow-hidden">
        <div class="mx-auto mt-12 flex max-w-7xl flex-col items-center">
            <h1
                class="mb-6 text-center text-2xl font-semibold text-[#137DC1] sm:text-3xl md:text-4xl lg:text-5xl"
            >
                {{ ewfLeader.title }}
            </h1>

            <div class="flex flex-col gap-4 text-center">
                <p
                    v-for="(paragraph, index) in ewfLeader.paragraphs"
                    :key="index"
                    class="text-base leading-relaxed text-gray-900 transition-all duration-500 md:text-lg dark:text-gray-300"
                >
                    {{ paragraph }}
                </p>
            </div>

            <img
                :src="ewfLeader.image"
                :alt="ewfLeader.imageAlt"
                class="mt-8 w-full max-w-4xl rounded-2xl object-cover shadow-lg"
                loading="lazy"
            />

            <div
                class="mt-8 flex w-full flex-col justify-center gap-4 sm:w-auto sm:flex-row sm:gap-6"
            >
                <a
                    v-for="(link, index) in ewfLeader.links"
                    :key="index"
                    :href="link.url"
                    target="_blank"
                    rel="noopener noreferrer"
                    :class="[
                        'inline-flex w-full cursor-pointer items-center justify-center gap-2 rounded-xl px-8 py-3.5 text-base font-medium shadow-md transition-all duration-300 hover:-translate-y-1 hover:shadow-lg sm:w-auto md:text-lg',
                        link.bgColor,
                        link.hoverColor,
                        link.textColor,
                    ]"
                >
                    {{ link.text }}
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-5 w-5"
                        viewBox="0 0 20 20"
                        fill="currentColor"
                    >
                        <path
                            fill-rule="evenodd"
                            d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z"
                            clip-rule="evenodd"
                        />
                    </svg>
                </a>
            </div>
        </div>

        <div class="mx-auto mt-20 flex max-w-7xl flex-col items-center">
            <h1
                class="mb-6 text-center text-2xl font-semibold text-[#137DC1] sm:text-3xl md:text-4xl lg:text-5xl"
            >
                {{ pdrciEsports.title }}
            </h1>

            <div class="flex flex-col gap-4 text-center">
                <p
                    v-for="(paragraph, index) in pdrciEsports.paragraphs"
                    :key="index"
                    class="text-base leading-relaxed text-gray-900 transition-all duration-500 md:text-lg dark:text-gray-300"
                >
                    {{ paragraph }}
                </p>
            </div>
        </div>

        <div
            class="relative mx-auto mt-10 flex h-80 w-full max-w-400 items-center overflow-hidden md:h-120"
        >
            <div
                v-for="(imgSrc, index) in pdrciEsports.carouselItems"
                :key="index"
                class="absolute top-1/2 box-border -translate-y-1/2 cursor-pointer overflow-hidden rounded-xl border-4 border-white bg-white shadow-md transition-all duration-700 ease-in-out"
                :class="getPosClass(index)"
                @click="currentIndex = index"
            >
                <img
                    :src="imgSrc"
                    alt="MOA Signing"
                    class="h-full w-full object-cover"
                    loading="lazy"
                />
            </div>
        </div>

        <div class="mx-auto mt-8 flex max-w-7xl flex-col items-center">
            <div
                class="flex w-full flex-col justify-center gap-4 sm:w-auto sm:flex-row sm:gap-6"
            >
                <a
                    v-for="(link, index) in pdrciEsports.links"
                    :key="index"
                    :href="link.url"
                    target="_blank"
                    rel="noopener noreferrer"
                    :class="[
                        'inline-flex w-full cursor-pointer items-center justify-center gap-2 rounded-xl px-8 py-3.5 text-base font-medium shadow-md transition-all duration-300 hover:-translate-y-1 hover:shadow-lg sm:w-auto md:text-lg',
                        link.bgColor,
                        link.hoverColor,
                        link.textColor,
                    ]"
                >
                    {{ link.text }}
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-5 w-5"
                        viewBox="0 0 20 20"
                        fill="currentColor"
                    >
                        <path
                            fill-rule="evenodd"
                            d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z"
                            clip-rule="evenodd"
                        />
                    </svg>
                </a>
            </div>
        </div>

        <div class="mx-auto flex max-w-7xl flex-col items-center">
            <h1
                class="my-4 text-center text-2xl font-semibold text-[#137DC1] sm:text-3xl md:text-4xl lg:text-5xl"
            >
                {{ article.title }}
            </h1>

            <div class="flex flex-col text-center">
                <p
                    v-for="(paragraph, index) in article.paragraphs"
                    :key="index"
                    class="text-base leading-relaxed text-gray-900 transition-all duration-500 md:text-lg dark:text-gray-300"
                >
                    {{ paragraph }}
                </p>
            </div>

            <div
                class="mt-2 flex flex-wrap justify-center gap-x-6 gap-y-2 text-sm font-medium text-gray-800 md:text-base dark:text-white"
            >
                <p>June 29, 2023</p>
            </div>
            <div class="mt-8 grid w-full max-w-6xl grid-cols-3 gap-3">
                <div
                    v-for="(card, index) in article.images"
                    :key="index"
                    :class="[
                        'overflow-hidden rounded-3xl transition-all duration-300 hover:-translate-y-1 hover:shadow-xl',
                        index === 0 ? 'col-span-3' : 'col-span-1',
                    ]"
                >
                    <img
                        :src="card"
                        alt="ESWF Collaboration Image"
                        class="h-full w-full object-cover"
                        :class="
                            index === 0
                                ? 'aspect-video max-h-125'
                                : 'aspect-square sm:aspect-video'
                        "
                    />
                </div>
            </div>
            <div class="mt-12 flex justify-center pb-2">
                <a
                    :href="article.actionLink"
                    target="_blank"
                    rel="noopener noreferrer"
                    class="inline-flex items-center gap-2 rounded-lg bg-[#137DC1] px-10 py-2 text-base font-medium text-white transition-all duration-300 hover:-translate-y-1 hover:bg-[#4089f7] md:text-lg"
                >
                    {{ article.actionText }}
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-5 w-5"
                        viewBox="0 0 20 20"
                        fill="currentColor"
                    >
                        <path
                            fill-rule="evenodd"
                            d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z"
                            clip-rule="evenodd"
                        />
                    </svg>
                </a>
            </div>
        </div>

        <div class="w-full transition-colors duration-500">
            <div
                class="w-full bg-linear-to-b from-transparent from-50% to-[#137DC1] to-50%"
            >
                <div class="mx-auto w-full max-w-7xl px-6 pt-4 sm:px-12">
                    <div
                        class="grid w-full grid-cols-1 gap-6 shadow-xl shadow-blue-500 md:grid-cols-3"
                    >
                        <div
                            v-for="(item, index) in licenses.images"
                            :key="index"
                            class="group relative flex aspect-square w-full overflow-hidden rounded-2xl bg-white shadow-xl transition-all duration-300 hover:-translate-y-1 hover:shadow-2xl"
                        >
                            <img
                                :src="item.url"
                                :alt="item.title"
                                class="h-full w-full object-cover transition-transform duration-500 ease-out group-hover:scale-105"
                                loading="lazy"
                            />

                            <div
                                class="pointer-events-none absolute inset-0 bg-linear-to-t from-black/90 via-black/20 to-transparent"
                            ></div>

                            <div class="absolute bottom-3 left-4 z-20 pr-4">
                                <h3
                                    class="text-sm font-medium text-white drop-shadow-md sm:text-base md:text-lg"
                                >
                                    ESWF {{ item.title }}
                                </h3>
                            </div>

                            <button
                                @click="forceDownload(item.url, index)"
                                class="absolute top-3 right-3 z-20 flex items-center gap-1.5 rounded-lg bg-[#E94140] px-3 py-1.5 text-xs font-bold text-white shadow-md transition-all duration-300 hover:scale-105 hover:bg-red-500 sm:text-sm"
                                title="Download Image"
                            >
                                <svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    class="h-4 w-4 sm:h-5 sm:w-5"
                                    viewBox="0 0 20 20"
                                    fill="currentColor"
                                >
                                    <path
                                        fill-rule="evenodd"
                                        d="M3 17a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zm3.293-7.707a1 1 0 011.414 0L9 10.586V3a1 1 0 112 0v7.586l1.293-1.293a1 1 0 111.414 1.414l-3 3a1 1 0 01-1.414 0l-3-3a1 1 0 010-1.414z"
                                        clip-rule="evenodd"
                                    />
                                </svg>
                                Download
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <div class="flex w-full flex-col items-center bg-[#137DC1]">
                <div
                    class="mx-auto w-full max-w-5xl px-4 py-10 text-center sm:px-6 md:py-16 lg:px-8"
                >
                    <div
                        class="mb-12 flex flex-col items-center justify-center gap-4 sm:flex-row sm:gap-6"
                    >
                        <h2
                            class="text-xl font-semibold text-white drop-shadow-sm sm:text-2xl md:text-3xl"
                        >
                            {{ licenses.title[0] }}
                        </h2>

                        <a
                            :href="licenses.download.link[0]"
                            :download="licenses.download.filename[0]"
                            target="_blank"
                            rel="noopener noreferrer"
                            class="flex shrink-0 items-center gap-2 rounded-lg border-2 border-white bg-[#E94140] px-6 py-2 text-sm font-bold text-white shadow-md transition-all duration-300 hover:-translate-y-1 hover:bg-red-500 hover:shadow-lg md:text-base"
                            title="Download Permit 1"
                        >
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                class="h-5 w-5"
                                viewBox="0 0 20 20"
                                fill="currentColor"
                                aria-hidden="true"
                            >
                                <path
                                    fill-rule="evenodd"
                                    d="M3 17a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zm3.293-7.707a1 1 0 011.414 0L9 10.586V3a1 1 0 112 0v7.586l1.293-1.293a1 1 0 111.414 1.414l-3 3a1 1 0 01-1.414 0l-3-3a1 1 0 010-1.414z"
                                    clip-rule="evenodd"
                                />
                            </svg>
                            Download
                        </a>
                    </div>

                    <div class="mx-auto mb-12 max-w-5xl space-y-3">
                        <h2
                            class="text-2xl font-bold tracking-wide text-white sm:text-3xl md:text-4xl"
                        >
                            {{ licenses.license }}
                        </h2>

                        <div
                            class="space-y-4 text-base leading-relaxed font-medium text-white/95 sm:text-lg md:text-xl"
                        >
                            <p
                                v-for="(
                                    paragraph, index
                                ) in licenses.paragraphs"
                                :key="index"
                            >
                                {{ paragraph }}
                            </p>
                        </div>
                    </div>

                    <div
                        class="flex flex-col items-center justify-center gap-4 sm:flex-row sm:gap-6"
                    >
                        <h2
                            class="text-xl font-semibold text-white drop-shadow-sm sm:text-2xl md:text-3xl"
                        >
                            {{ licenses.title[1] }}
                        </h2>

                        <a
                            :href="licenses.download.link[1]"
                            :download="licenses.download.filename[1]"
                            target="_blank"
                            rel="noopener noreferrer"
                            class="flex shrink-0 items-center gap-2 rounded-lg border-2 border-white bg-[#E94140] px-6 py-2 text-sm font-bold text-white shadow-md transition-all duration-300 hover:-translate-y-1 hover:bg-red-500 hover:shadow-lg md:text-base"
                            title="Download Permit 2"
                        >
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                class="h-5 w-5"
                                viewBox="0 0 20 20"
                                fill="currentColor"
                                aria-hidden="true"
                            >
                                <path
                                    fill-rule="evenodd"
                                    d="M3 17a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zm3.293-7.707a1 1 0 011.414 0L9 10.586V3a1 1 0 112 0v7.586l1.293-1.293a1 1 0 111.414 1.414l-3 3a1 1 0 01-1.414 0l-3-3a1 1 0 010-1.414z"
                                    clip-rule="evenodd"
                                />
                            </svg>
                            Download
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
