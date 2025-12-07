<script lang="ts">
  const columns = [
    [
      {
        title: "Shop and Learn",
        links: ["Store", "Mac", "iPad", "iPhone", "Watch", "Vision", "AirPods", "TV & Home", "AirTag", "Accessories", "Gift Cards"]
      },
      {
        title: "Apple Wallet",
        links: ["Wallet", "Apple Card", "Apple Pay", "Apple Cash"]
      }
    ],
    [
      {
        title: "Account",
        links: ["Manage Your Apple Account", "Apple Store Account", "iCloud.com"]
      },
      {
        title: "Entertainment",
        links: ["Apple One", "Apple TV+", "Apple Music", "Apple Arcade", "Apple Fitness+", "Apple News+", "Apple Podcasts", "Apple Books", "App Store"]
      }
    ],
    [
      {
        title: "Apple Store",
        links: ["Find a Store", "Genius Bar", "Today at Apple", "Group Reservations", "Apple Camp", "Apple Store App", "Certified Refurbished", "Apple Trade In", "Financing", "Carrier Deals at Apple", "Order Status", "Shopping Help"]
      }
    ],
    [
      {
        title: "For Business",
        links: ["Apple and Business", "Shop for Business"]
      },
      {
        title: "For Education",
        links: ["Apple and Education", "Shop for K-12", "Shop for College"]
      },
      {
        title: "For Healthcare",
        links: ["Apple and Healthcare", "Health on Apple Watch", "Health Records on iPhone"]
      },
      {
        title: "For Government",
        links: ["Shop for Government", "Shop for Veterans and Military"]
      }
    ],
    [
      {
        title: "Apple Values",
        links: ["Accessibility", "Education", "Environment", "Inclusion and Diversity", "Privacy", "Racial Equity and Justice", "Supply Chain Innovation"]
      },
      {
        title: "About Apple",
        links: ["Newsroom", "Apple Leadership", "Career Opportunities", "Investors", "Ethics & Compliance", "Events", "Contact Apple"]
      }
    ]
  ];
</script>

<footer class="bg-[#f5f5f7] text-[#1d1d1f] text-[12px] leading-normal font-sans pt-10 pb-10">
  <div class="max-w-[980px] mx-auto px-4">
    
    <!-- Top Text -->
    <div class="border-b border-[#d2d2d7] pb-5 mb-5 space-y-2 text-[#6e6e73]">
       <p>1. Through December 7, 2025, Apple will donate $5 for every purchase made with Apple Pay at an Apple Store, in the Apple Store app, or on <a href="/" class="underline text-[#1d1d1f]">apple.com</a>. Donations are limited to a maximum of three million dollars ($3,000,000). The donation goes to the Fund for the Global Fund to fight AIDS and help fund critical health programs that save lives.</p>
       <p>2. Trade-in values will vary based on the condition, year, and configuration of your eligible trade-in device. Not all devices are eligible for credit. You must be at least the age of majority to be eligible to trade in for credit or for an Apple Gift Card. Trade-in value may be applied toward qualifying new device purchase, or added to an Apple Gift Card. Actual value awarded is based on receipt of a qualifying device matching the description provided when estimate was made. Sales tax may be assessed on full value of a new device purchase. In-store trade-in requires presentation of a valid photo ID (local law may require saving this information). Offer may not be available in all stores and may vary between in-store and online trade-in. Some stores may have additional requirements. Apple or its trade-in partners reserve the right to refuse, cancel, or limit quantity of any trade-in transaction for any reason. More details are available from Apple's trade-in partner for trade-in and recycling of eligible devices. Restrictions and limitations may apply.</p>
       <p>To access and use all Apple Card features and products available only to Apple Card users, you must add Apple Card to Wallet on an iPhone or iPad that supports and has the latest version of iOS or iPadOS. Apple Card is subject to credit approval, available only for qualifying applicants in the United States, and issued by Goldman Sachs Bank USA, Salt Lake City Branch.</p>
       <p>Apple Payments Services LLC, a subsidiary of Apple Inc., is a service provider of Goldman Sachs Bank USA for Apple Card and Savings accounts. Neither Apple Inc. nor Apple Payments Services LLC is a bank.</p>
       <p>If you reside in the U.S. territories, please call Goldman Sachs at 877-255-5923 with questions about Apple Card.</p>
       <p>Learn more about how Apple Card applications are evaluated at <a href="/" class="underline text-[#1d1d1f]">support.apple.com/kb/HT209218</a>.</p>
       <p>A subscription is required for Apple Arcade, Apple Fitness+, Apple Music, and Apple TV.</p>
       <p>Features are subject to change. Some features, applications, and services may not be available in all regions or all languages.</p>
    </div>

    <!-- Directory Columns -->
    <div class="grid grid-cols-2 md:grid-cols-5 gap-x-4 gap-y-8">
      {#each columns as col}
        <div class="flex flex-col gap-6">
          {#each col as section}
            <div>
              <h3 class="font-semibold text-[#1d1d1f] mb-2">{section.title}</h3>
              <ul class="space-y-1.5">
                {#each section.links as link}
                  <li><a href="/" class="text-[#424245] hover:underline">{link}</a></li>
                {/each}
              </ul>
            </div>
          {/each}
        </div>
      {/each}
    </div>

    <!-- Bottom Footer -->
    <div class="mt-8 pt-8 border-t border-[#d2d2d7]">
      <div class="mb-2 text-[#6e6e73]">
        More ways to shop: <a href="/" class="text-[#0066cc] hover:underline">Find an Apple Store</a> or <a href="/" class="text-[#0066cc] hover:underline">other retailer</a> near you. Or call 1-800-MY-APPLE.
      </div>
      
      <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mt-4 text-[#6e6e73]">
        <div class="order-2 md:order-1">
          Copyright © 2025 Apple Inc. All rights reserved.
        </div>
        <div class="flex flex-wrap gap-x-4 gap-y-2 order-1 md:order-2">
          <a href="/" class="hover:underline text-[#424245]">Privacy Policy</a>
          <span class="text-[#d2d2d7]">|</span>
          <a href="/" class="hover:underline text-[#424245]">Terms of Use</a>
          <span class="text-[#d2d2d7]">|</span>
          <a href="/" class="hover:underline text-[#424245]">Sales and Refunds</a>
          <span class="text-[#d2d2d7]">|</span>
          <a href="/" class="hover:underline text-[#424245]">Legal</a>
          <span class="text-[#d2d2d7]">|</span>
          <a href="/" class="hover:underline text-[#424245]">Site Map</a>
        </div>
        <div class="order-3 text-[#424245]">
          United States
        </div>
      </div>
    </div>
  </div>
</footer>
