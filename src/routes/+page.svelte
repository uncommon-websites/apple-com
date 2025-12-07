<script lang="ts">
    import Navbar from "$lib/components/Navbar.svelte";
    import NotificationBar from "$lib/components/NotificationBar.svelte";
    import Hero from "$lib/components/Hero.svelte";
    import ProductSection from "$lib/components/ProductSection.svelte";
    import GridItem from "$lib/components/GridItem.svelte";
    import Footer from "$lib/components/Footer.svelte";
    import Carousel from "$lib/components/Carousel.svelte";

    // Define the Link type to satisfy TypeScript
    type Link = { text: string; href: string; variant?: "filled" | "outline" };

    const iPhoneLinks: Link[] = [
        { text: "Learn more", href: "/", variant: "filled" },
        { text: "Shop iPhone", href: "/", variant: "outline" }
    ];

    const airPodsLinks: Link[] = [
        { text: "Learn more", href: "/", variant: "filled" },
        { text: "Buy", href: "/", variant: "outline" }
    ];

    const iPadAirLinks: Link[] = [
        { text: "Learn more", href: "/" },
        { text: "Buy", href: "/", variant: "outline" }
    ];

    const watchLinks: Link[] = [
        { text: "Learn more", href: "/" },
        { text: "Buy", href: "/", variant: "outline" }
    ];

    const iPadLinks: Link[] = [
        { text: "Learn more", href: "/" },
        { text: "Buy", href: "/", variant: "outline" }
    ];

    const macBookLinks: Link[] = [
        { text: "Learn more", href: "/" },
        { text: "Buy", href: "/", variant: "outline" }
    ];

    const tradeInLinks: Link[] = [
        { text: "Get your estimate", href: "/" }
    ];

    const cardLinks: Link[] = [
        { text: "Learn more", href: "/" },
        { text: "Apply now", href: "/", variant: "outline" }
    ];

    const carouselItems = [
        {
            gradient: "bg-gradient-to-r from-blue-900 to-gray-800", // Placeholder for Family Plan
            title: "THE FAMILY PLAN",
            subtitle: "Same family. New plan.",
            genre: "Action Comedy",
            type: "Apple TV+",
            textColor: "text-white",
            action: "Stream now"
        },
        {
            gradient: "bg-gradient-to-r from-gray-900 to-gray-600", // Placeholder for Sabrina
            title: "Sabrina Carpenter",
            subtitle: "The Zane Lowe Interview",
            type: "Apple Music",
            textColor: "text-white",
            action: "Listen now"
        },
        {
            gradient: "bg-gradient-to-r from-blue-800 to-purple-900", // Placeholder for NBA
            title: "NBA 2K24",
            subtitle: "Arcade Edition",
            type: "Apple Arcade",
            textColor: "text-white",
            action: "Play now"
        },
         {
            gradient: "bg-gradient-to-r from-pink-500 to-orange-400", // Placeholder for Fitness
            title: "Pilates",
            subtitle: "Improve Your Posture",
            type: "Apple Fitness+",
            textColor: "text-white",
            action: "Start workout"
        }
    ];
</script>

<div class="font-sans antialiased">
    <Navbar />
    <NotificationBar 
        text="For every Apple Pay purchase made at Apple, we're donating $5 to the Global Fund's fight against AIDS. Through 12/7." 
        linkText="Shop" 
    />

    <Hero 
        title="Give something special."
        subtitle="Find what they've been waiting for all year."
        buttons={[{ label: "Shop gifts", href: "/" }]}
        logo={true}
    >
        <div slot="logoContent" class="flex justify-center mb-6">
             <!-- Custom Gift Apple Logo -->
             <div class="relative w-[120px] h-[150px] md:w-[160px] md:h-[200px]">
                <!-- Apple Logo Shape with Gradient -->
                <svg viewBox="0 0 170 170" class="w-full h-full drop-shadow-2xl">
                    <defs>
                        <linearGradient id="giftGradient" x1="0%" y1="0%" x2="0%" y2="100%">
                            <stop offset="0%" style="stop-color:#4facfe;stop-opacity:1" /> <!-- Blue top -->
                            <stop offset="50%" style="stop-color:#f6d365;stop-opacity:1" /> <!-- Yellow middle -->
                            <stop offset="100%" style="stop-color:#fda085;stop-opacity:1" /> <!-- Orange bottom -->
                        </linearGradient>
                         <!-- More accurate gradient based on screenshot -->
                         <linearGradient id="appleGradient" x1="0%" y1="0%" x2="0%" y2="100%">
                            <stop offset="0%" style="stop-color:#00C6FB;stop-opacity:1" />
                            <stop offset="40%" style="stop-color:#FFED86;stop-opacity:1" />
                            <stop offset="100%" style="stop-color:#FF9D6C;stop-opacity:1" />
                        </linearGradient>
                    </defs>
                    <path fill="url(#appleGradient)" d="M150.37 130.25c-7.57 11.06-16.1 20.25-27.05 20.25-10.03 0-13.07-5.93-24.26-5.93-11.36 0-14.22 5.76-24.08 5.76-11.13 0-20.65-10.22-28.06-21.75-15.34-23.86-12.38-58.8 12.02-59.06 9.84-.11 16.94 6.47 22.45 6.47 5.34 0 13.56-6.84 22.95-6.84 3.88 0 15.11.39 22.25 10.84-18.06 10.76-15.06 32.32 2.06 39.11-.47 2.84-1.12 5.67-1.92 8.38-.81 2.76-1.78 5.48-2.91 8.12l-1.4 3.15zM110.86 52.55c-5.31 6.43-12.86 10.61-20.13 9.94-.96-6.35 2.37-12.98 7.33-17.16 4.96-4.17 12.34-7.46 19.12-6.81.96 6.64-2.51 13.08-6.32 14.03z"/>
                </svg>
                
                <!-- White Ribbon/Bow Overlay -->
                <div class="absolute top-[35%] left-1/2 -translate-x-1/2 w-[110%] h-[30px] bg-white/90 backdrop-blur-sm shadow-sm rotate-[-5deg] rounded-sm"></div>
                <!-- Vertical ribbon part -->
                <div class="absolute top-[10%] left-1/2 -translate-x-1/2 w-[30px] h-[80%] bg-white/90 backdrop-blur-sm shadow-sm rounded-sm"></div>
                
                <!-- Bow Center -->
                <div class="absolute top-[35%] left-1/2 -translate-x-1/2 -translate-y-1/2 w-12 h-12 bg-white rounded-full shadow-md z-10 flex items-center justify-center">
                    <div class="w-2 h-2 bg-gray-200 rounded-full"></div>
                </div>
                
                <!-- Bow Loops (CSS approximation) -->
                <div class="absolute top-[20%] left-[20%] w-16 h-16 border-[6px] border-white rounded-tl-[40px] rounded-bl-[40px] rotate-[-15deg]"></div>
                <div class="absolute top-[20%] right-[20%] w-16 h-16 border-[6px] border-white rounded-tr-[40px] rounded-br-[40px] rotate-[15deg]"></div>
             </div>
        </div>
    </Hero>

    <!-- iPhone Section -->
    <ProductSection 
        title="iPhone" 
        subtitle="Say hello to the latest generation of iPhone."
        links={iPhoneLinks}
    >
        <div slot="image" class="relative w-full h-[300px] md:h-[500px] flex justify-center items-end">
             <!-- Placeholder for iPhones -->
             <div class="flex gap-4 md:gap-10 items-end">
                <!-- iPhone Pro -->
                <div class="w-[140px] md:w-[220px] h-[280px] md:h-[440px] bg-gray-800 rounded-[30px] md:rounded-[40px] border-4 border-gray-600 relative shadow-2xl">
                    <div class="absolute top-4 left-1/2 -translate-x-1/2 w-[30%] h-[20px] bg-black rounded-b-xl"></div>
                    <!-- Screen content simulation -->
                    <div class="w-full h-full rounded-[26px] md:rounded-[36px] overflow-hidden bg-gradient-to-br from-blue-900 to-black opacity-80"></div>
                </div>
                <!-- iPhone Standard -->
                <div class="w-[140px] md:w-[220px] h-[280px] md:h-[440px] bg-pink-100 rounded-[30px] md:rounded-[40px] border-4 border-pink-200 relative shadow-2xl">
                    <div class="absolute top-4 left-1/2 -translate-x-1/2 w-[30%] h-[20px] bg-black rounded-b-xl"></div>
                    <div class="w-full h-full rounded-[26px] md:rounded-[36px] overflow-hidden bg-gradient-to-br from-pink-200 to-white opacity-80"></div>
                </div>
             </div>
        </div>
    </ProductSection>

    <!-- AirPods Pro 3 Section -->
    <ProductSection 
        title="AirPods Pro 3" 
        subtitle="The world's best in-ear Active Noise Cancellation."
        links={airPodsLinks}
    >
        <div slot="image" class="relative w-full h-[300px] md:h-[500px] flex justify-center items-center">
             <div class="flex gap-10 md:gap-20">
                 <!-- Left AirPod -->
                 <div class="w-[100px] md:w-[150px] h-[120px] md:h-[180px] bg-white rounded-full relative shadow-lg transform -rotate-12">
                     <div class="absolute top-1/4 right-0 w-4 h-10 bg-black rounded-l-lg opacity-20"></div>
                     <div class="absolute bottom-[-40px] right-2 w-4 h-16 bg-white border border-gray-200 rounded-b-full transform rotate-12"></div>
                 </div>
                 <!-- Right AirPod -->
                 <div class="w-[100px] md:w-[150px] h-[120px] md:h-[180px] bg-white rounded-full relative shadow-lg transform rotate-12">
                     <div class="absolute top-1/4 left-0 w-4 h-10 bg-black rounded-r-lg opacity-20"></div>
                     <div class="absolute bottom-[-40px] left-2 w-4 h-16 bg-white border border-gray-200 rounded-b-full transform -rotate-12"></div>
                 </div>
             </div>
        </div>
    </ProductSection>

    <!-- Grid Section 1 -->
    <div class="grid grid-cols-1 md:grid-cols-2 gap-3 px-3 pb-3 bg-white">
        <!-- iPad Air -->
        <GridItem 
            subtitle="Now supercharged by the M3 chip."
            links={iPadAirLinks}
            backgroundClass="bg-[#fbfbfd]"
        >
            <div slot="logo" class="flex items-center justify-center gap-1">
                <span class="text-[32px] md:text-[40px] font-semibold tracking-tight">iPad</span>
                <span class="text-[32px] md:text-[40px] font-light italic text-[#0071e3] font-serif">air</span>
            </div>

            <div slot="image" class="w-full h-[300px] md:h-[400px] relative overflow-hidden flex justify-center items-end pb-8">
                <!-- Simulated iPad Airs fanned out -->
                 <div class="relative w-[300px] h-[200px]">
                     <div class="absolute top-0 left-10 w-[200px] h-[150px] bg-blue-200 rounded-lg transform -rotate-12 border border-gray-300 shadow-md"></div>
                     <div class="absolute top-4 left-20 w-[200px] h-[150px] bg-purple-200 rounded-lg transform -rotate-6 border border-gray-300 shadow-md"></div>
                     <div class="absolute top-8 left-30 w-[200px] h-[150px] bg-gray-100 rounded-lg transform rotate-0 border border-gray-300 shadow-md flex items-center justify-center">
                        <div class="w-[90%] h-[90%] bg-gradient-to-br from-blue-100 to-pink-100 rounded"></div>
                     </div>
                 </div>
            </div>
        </GridItem>

        <!-- Watch Series 11 -->
        <GridItem 
            subtitle="The ultimate way to watch your health."
            links={watchLinks}
            backgroundClass="bg-[#fbfbfd]"
        >
            <div slot="logo" class="flex items-center justify-center gap-2">
                <svg class="h-8 w-auto fill-black" viewBox="0 0 17 17" xmlns="http://www.w3.org/2000/svg"><path d="M15.5752 16.034C14.7336 17.266 13.7852 18.25 12.5684 18.25C11.4556 18.25 11.1204 17.594 9.8756 17.594C8.614 17.594 8.2468 18.234 7.234 18.25C5.9724 18.266 4.9068 17.134 4.0708 15.922C2.3652 13.45 1.07 9.682 2.8076 6.666C3.6684 5.17 5.2188 4.218 6.9068 4.218C8.1036 4.218 9.0708 5.034 9.8084 5.034C10.514 5.034 11.7268 4.09 13.1524 4.09C13.7252 4.09 15.3652 4.298 16.3652 5.762C16.2852 5.81 14.4652 6.874 14.4652 9.61C14.4652 12.874 17.2652 13.978 17.3324 14.01C17.2844 14.17 16.8684 15.634 16.3652 16.362L15.5752 16.034ZM11.422 4.202C12.0452 3.442 12.4372 2.394 12.3252 1.33C11.3324 1.37 10.1852 1.994 9.482 2.85C8.8908 3.53 8.4428 4.61 8.5868 5.65C9.6428 5.73 10.766 5.01 11.422 4.202Z" transform="translate(-2 -1)" /></svg>
                <div class="flex flex-col items-start leading-none">
                    <span class="text-[19px] font-semibold tracking-tight uppercase">Watch</span>
                    <span class="text-[10px] font-semibold tracking-widest text-red-600 uppercase">Series 11</span>
                </div>
            </div>

            <div slot="image" class="w-full h-[300px] md:h-[400px] flex justify-center items-center">
                 <div class="w-[240px] h-[140px] relative">
                     <!-- Watch Band -->
                     <div class="absolute top-1/2 left-0 w-full h-[60px] -translate-y-1/2 bg-[#e0e0e0] rounded-full shadow-inner"></div>
                     <!-- Watch Body -->
                     <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[100px] h-[120px] bg-[#d4af37] rounded-[24px] shadow-xl flex items-center justify-center border border-[#c5a028]">
                         <!-- Screen -->
                         <div class="w-[90px] h-[110px] bg-black rounded-[20px] overflow-hidden relative">
                             <!-- Rings -->
                             <div class="absolute inset-0 flex items-center justify-center">
                                 <div class="w-16 h-16 rounded-full border-4 border-red-500 border-t-transparent rotate-45"></div>
                                 <div class="absolute w-12 h-12 rounded-full border-4 border-green-500 border-r-transparent -rotate-12"></div>
                                 <div class="absolute w-8 h-8 rounded-full border-4 border-blue-500 border-b-transparent rotate-90"></div>
                             </div>
                         </div>
                     </div>
                     <!-- Crown -->
                     <div class="absolute top-[30%] right-[60px] w-3 h-8 bg-[#d4af37] rounded-r-sm"></div>
                 </div>
            </div>
        </GridItem>

        <!-- iPad -->
        <GridItem 
            title="iPad"
            subtitle="Now with the speed of the A16 chip and double the starting storage."
            links={iPadLinks}
            backgroundClass="bg-white"
        >
            <div slot="image" class="w-full h-[300px] md:h-[400px] flex justify-center items-end pb-4">
                <div class="relative w-[300px] h-[200px]">
                    <div class="absolute bottom-0 left-1/2 -translate-x-1/2 flex items-end justify-center space-x-[-40px]">
                        <div class="w-[140px] h-[190px] bg-yellow-400 rounded-lg transform -rotate-12 border border-gray-200 shadow-lg origin-bottom-right"></div>
                        <div class="w-[140px] h-[190px] bg-pink-400 rounded-lg transform -rotate-6 border border-gray-200 shadow-lg origin-bottom-right z-10"></div>
                        <div class="w-[140px] h-[190px] bg-blue-400 rounded-lg transform rotate-0 border border-gray-200 shadow-lg z-20 flex items-center justify-center">
                            <div class="w-[90%] h-[90%] bg-black rounded overflow-hidden">
                                <div class="w-full h-full bg-gradient-to-br from-purple-500 to-blue-500 opacity-50"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </GridItem>

        <!-- MacBook Air -->
        <GridItem 
            title="MacBook Air"
            subtitle="Sky blue color. Sky high performance with M4."
            links={macBookLinks}
            backgroundClass="bg-[#f0f8ff]"
        >
            <div slot="image" class="w-full h-[300px] md:h-[400px] flex justify-center items-center">
                 <div class="relative w-[320px] h-[200px] flex flex-col items-center justify-center">
                     <!-- Open MacBook -->
                     <div class="relative w-[280px]">
                         <!-- Screen -->
                         <div class="w-[240px] h-[160px] bg-black rounded-t-xl mx-auto border-4 border-gray-300 border-b-0 relative z-10 shadow-xl">
                             <div class="w-full h-full bg-blue-100 overflow-hidden relative">
                                 <div class="absolute inset-0 bg-gradient-to-tr from-blue-200 to-white opacity-50"></div>
                             </div>
                         </div>
                         <!-- Base -->
                         <div class="w-[280px] h-3 bg-gray-300 rounded-b-xl shadow-2xl relative z-20">
                             <div class="absolute top-0 left-1/2 -translate-x-1/2 w-10 h-1 bg-gray-400 rounded-b-sm"></div>
                         </div>
                     </div>
                     <!-- Closed MacBook (Side profile) -->
                     <div class="absolute bottom-[-20px] right-[-20px] w-[260px] h-2 bg-blue-200 rounded-full shadow-lg transform rotate-3"></div>
                 </div>
            </div>
        </GridItem>

        <!-- Trade In -->
        <GridItem 
            subtitle="Get up to $180-$670 in credit when you trade in iPhone 13 or higher."
            links={tradeInLinks}
            backgroundClass="bg-white"
        >
            <div slot="logo" class="flex items-center justify-center gap-2">
                <svg class="h-8 w-auto fill-black" viewBox="0 0 17 17" xmlns="http://www.w3.org/2000/svg"><path d="M15.5752 16.034C14.7336 17.266 13.7852 18.25 12.5684 18.25C11.4556 18.25 11.1204 17.594 9.8756 17.594C8.614 17.594 8.2468 18.234 7.234 18.25C5.9724 18.266 4.9068 17.134 4.0708 15.922C2.3652 13.45 1.07 9.682 2.8076 6.666C3.6684 5.17 5.2188 4.218 6.9068 4.218C8.1036 4.218 9.0708 5.034 9.8084 5.034C10.514 5.034 11.7268 4.09 13.1524 4.09C13.7252 4.09 15.3652 4.298 16.3652 5.762C16.2852 5.81 14.4652 6.874 14.4652 9.61C14.4652 12.874 17.2652 13.978 17.3324 14.01C17.2844 14.17 16.8684 15.634 16.3652 16.362L15.5752 16.034ZM11.422 4.202C12.0452 3.442 12.4372 2.394 12.3252 1.33C11.3324 1.37 10.1852 1.994 9.482 2.85C8.8908 3.53 8.4428 4.61 8.5868 5.65C9.6428 5.73 10.766 5.01 11.422 4.202Z" transform="translate(-2 -1)" /></svg>
                <span class="text-[32px] md:text-[40px] font-semibold tracking-tight">Trade In</span>
            </div>

            <div slot="image" class="w-full h-[300px] md:h-[400px] flex justify-center items-center">
                <div class="relative">
                    <div class="w-[140px] h-[280px] bg-white border border-gray-300 rounded-[30px] shadow-xl flex items-center justify-center overflow-hidden">
                        <div class="w-full h-full bg-gray-50 flex flex-col items-center pt-8">
                             <div class="w-20 h-20 rounded-full bg-gray-200 mb-4"></div>
                             <div class="w-24 h-4 bg-gray-200 rounded mb-2"></div>
                             <div class="w-16 h-4 bg-gray-200 rounded"></div>
                        </div>
                    </div>
                    <!-- Hand simulation or just another phone -->
                    <div class="absolute top-10 -right-10 w-[140px] h-[280px] bg-white border border-gray-300 rounded-[30px] shadow-xl transform rotate-12 z-[-1]"></div>
                </div>
            </div>
        </GridItem>

        <!-- Apple Card -->
        <GridItem 
            subtitle="Get up to 3% Daily Cash back with every purchase."
            links={cardLinks}
            backgroundClass="bg-white"
        >
            <div slot="logo" class="flex items-center justify-center gap-2">
                <svg class="h-8 w-auto fill-black" viewBox="0 0 17 17" xmlns="http://www.w3.org/2000/svg"><path d="M15.5752 16.034C14.7336 17.266 13.7852 18.25 12.5684 18.25C11.4556 18.25 11.1204 17.594 9.8756 17.594C8.614 17.594 8.2468 18.234 7.234 18.25C5.9724 18.266 4.9068 17.134 4.0708 15.922C2.3652 13.45 1.07 9.682 2.8076 6.666C3.6684 5.17 5.2188 4.218 6.9068 4.218C8.1036 4.218 9.0708 5.034 9.8084 5.034C10.514 5.034 11.7268 4.09 13.1524 4.09C13.7252 4.09 15.3652 4.298 16.3652 5.762C16.2852 5.81 14.4652 6.874 14.4652 9.61C14.4652 12.874 17.2652 13.978 17.3324 14.01C17.2844 14.17 16.8684 15.634 16.3652 16.362L15.5752 16.034ZM11.422 4.202C12.0452 3.442 12.4372 2.394 12.3252 1.33C11.3324 1.37 10.1852 1.994 9.482 2.85C8.8908 3.53 8.4428 4.61 8.5868 5.65C9.6428 5.73 10.766 5.01 11.422 4.202Z" transform="translate(-2 -1)" /></svg>
                <span class="text-[32px] md:text-[40px] font-semibold tracking-tight">Card</span>
            </div>

            <div slot="image" class="w-full h-[300px] md:h-[400px] flex justify-center items-center">
                <div class="w-[280px] h-[170px] bg-gray-50 rounded-xl shadow-xl border border-gray-200 flex items-center justify-center relative overflow-hidden transform rotate-6 hover:rotate-0 transition-transform duration-500">
                    <div class="absolute top-4 left-4">
                        <svg class="w-6 h-6 fill-gray-300" viewBox="0 0 17 17"><path d="M15.5752 16.034C14.7336 17.266 13.7852 18.25 12.5684 18.25C11.4556 18.25 11.1204 17.594 9.8756 17.594C8.614 17.594 8.2468 18.234 7.234 18.25C5.9724 18.266 4.9068 17.134 4.0708 15.922C2.3652 13.45 1.07 9.682 2.8076 6.666C3.6684 5.17 5.2188 4.218 6.9068 4.218C8.1036 4.218 9.0708 5.034 9.8084 5.034C10.514 5.034 11.7268 4.09 13.1524 4.09C13.7252 4.09 15.3652 4.298 16.3652 5.762C16.2852 5.81 14.4652 6.874 14.4652 9.61C14.4652 12.874 17.2652 13.978 17.3324 14.01C17.2844 14.17 16.8684 15.634 16.3652 16.362L15.5752 16.034ZM11.422 4.202C12.0452 3.442 12.4372 2.394 12.3252 1.33C11.3324 1.37 10.1852 1.994 9.482 2.85C8.8908 3.53 8.4428 4.61 8.5868 5.65C9.6428 5.73 10.766 5.01 11.422 4.202Z" transform="translate(-2 -1)" /></svg>
                    </div>
                    <div class="absolute bottom-4 left-4 text-xs text-gray-400 font-medium">Marisa Robertson</div>
                </div>
            </div>
        </GridItem>
    </div>

    <Carousel items={carouselItems} />
    <Footer />
</div>

