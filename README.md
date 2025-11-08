<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PRVT TRANSPORT - Reliable Trucking Services</title>
    <!-- Load Tailwind CSS --><script src="https://cdn.tailwindcss.com"></script>
    <!-- Configure Tailwind for custom colors and font --><script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'primary-green': '#047857', // Emerald 700
                        'dark-green': '#064e3b',   // Emerald 900
                        'light-bg': '#f0fdf4',     // Emerald 50
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                }
            }
        }
    </script>
    <style>
        /* Apply the Inter font globally */
        body {
            font-family: 'Inter', 'sans-serif';
            background-color: #ffffff; /* White base */
        }
        /* Ensure date input text is visible and matches style */
        input[type="date"] {
            color: #4b5563; /* Gray-600 */
        }
        /* Simple Modal Styling */
        .modal-overlay {
            background-color: rgba(0, 0, 0, 0.75);
        }
        /* Utility class to display status pill colors */
        .status-pill {
            display: inline-block;
            padding: 2px 8px;
            border-radius: 9999px;
            font-size: 0.75rem;
            font-weight: 600;
        }
        .status-New { background-color: #fcd34d; color: #92400e; } /* Amber */
        .status-Quoted { background-color: #3b82f6; color: #ffffff; } /* Blue */
        .status-Booked { background-color: #f97316; color: #ffffff; } /* Orange */
        .status-In-Transit { background-color: #10b981; color: #ffffff; } /* Emerald */
        .status-Delivered { background-color: #1d4ed8; color: #ffffff; } /* Royal Blue */
        .status-Cancelled { background-color: #ef4444; color: #ffffff; } /* Red */
    </style>
</head>
<body class="text-gray-800">

    <!-- Header & Navigation --><header class="bg-primary-green shadow-lg sticky top-0 z-10">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex justify-between items-center">
            <!-- Logo / Brand Name --><div class="flex items-center space-x-2">
                <img src="uploaded:image.png-57ea81b9-5b14-48f3-9118-59e43fdf5937" alt="PRVT Transport Logo" class="h-10">
            </div>
            <!-- Desktop Navigation Links --><nav class="hidden md:flex space-x-6">
                <a href="#services" class="text-white hover:text-dark-green transition duration-300 font-medium">Services</a>
                <a href="#about" class="text-white hover:text-dark-green transition duration-300 font-medium">Why Us</a>
                <a href="#contact" class="text-white hover:text-dark-green transition duration-300 font-medium">Contact</a>
                <!-- ADMIN LINK --><button onclick="openAdminModal()" class="text-white hover:text-dark-green transition duration-300 font-bold bg-dark-green px-3 py-1 rounded-lg">Admin</button>
            </nav>
            <!-- Mobile Navigation -->
            <div class="md:hidden flex">
                <!-- Hamburger Menu Button (The three bars) --><button id="mobile-menu-button" onclick="toggleMobileMenu()" class="text-white focus:outline-none p-2 rounded-lg bg-dark-green hover:bg-primary-green transition">
                    <!-- Hamburger Icon --><svg class="w-6 h-6" id="menu-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path></svg>
                </button>
            </div>
        </div>
        <!-- Mobile Menu Content --><div id="mobile-menu-content" class="md:hidden hidden bg-dark-green w-full pb-2">
            <a href="#services" onclick="toggleMobileMenu()" class="block px-4 py-2 text-white hover:bg-primary-green transition duration-300 font-medium">Services</a>
            <a href="#about" onclick="toggleMobileMenu()" class="block px-4 py-2 text-white hover:bg-primary-green transition duration-300 font-medium">Why Us</a>
            <a href="#contact" onclick="toggleMobileMenu()" class="block px-4 py-2 text-white hover:bg-primary-green transition duration-300 font-medium">Contact</a>
            
            <!-- NEW CONTACT INFO BLOCK for Mobile Menu -->
            <div class="px-4 pt-3 pb-4 border-t border-primary-green/50 mt-2 mx-4 rounded-lg bg-dark-green/80">
                <p class="text-sm font-bold text-white mb-2">Get in Touch:</p>
                <a href="tel:9084606880" class="flex items-center text-primary-green font-semibold text-sm hover:text-white transition mb-1">
                    <svg class="w-4 h-4 mr-2" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M2 3a1 1 0 011-1h2.153a1 1 0 01.986.836l.74 4.435a1 1 0 01-.54 1.06l-1.548.773a11.037 11.037 0 006.105 6.105l.774-1.548a1 1 0 011.059-.54l4.435.74A1 1 0 0118 16.847V17a1 1 0 01-1 1h-2C7.82 18 2 12.18 2 5V3z"></path></svg>
                    (908) 460-6880
                </a>
                <a href="mailto:Booking@prvttransport.com" class="flex items-center text-primary-green font-semibold text-sm hover:text-white transition">
                    <svg class="w-4 h-4 mr-2" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z"></path><path d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h16a2 2 0 002-2V8.118z"></path></svg>
                    Email Us
                </a>
                <p class="text-xs text-gray-400 mt-2">2 Arnot st , Lodi ,NJ 07644</p>
            </div>
            
            <button onclick="openAdminModal(); toggleMobileMenu();" class="block w-full text-left px-4 py-2 text-white hover:bg-primary-green transition duration-300 font-medium">Admin</button>
        </div>
    </header>

    <!-- Hero Section (White background, Green Call-to-Action) --><section class="bg-white py-16 md:py-24 text-center">
        <div class="max-w-4xl mx-auto px-4">
            <h2 class="text-4xl sm:text-5xl font-extrabold text-dark-green mb-4 leading-tight">
                Driving Your Success, Mile After Mile.
            </h2>
            <!-- Updated Hero Text --><p class="text-xl text-gray-600 mb-8 max-w-2xl mx-auto">
                We provide reliable, efficient, and fully-insured local and long-distance freight solutions all around the United States. Dependable delivery for every mile.
            </p>
            <a href="#contact" class="inline-block px-8 py-3 bg-primary-green text-white font-bold rounded-xl shadow-lg hover:bg-dark-green transition duration-300 transform hover:scale-105">
                Get a Free Quote Today
            </a>
            <!-- Placeholder Image: A Truck for visual appeal --><img src="https://placehold.co/800x400/064e3b/ffffff?text=Reliable+Fleet"
                 alt="Large semi-truck driving on the highway"
                 class="mt-12 w-full rounded-2xl shadow-2xl object-cover h-48 md:h-96"
                 onerror="this.onerror=null;this.src='https://placehold.co/800x400/064e3b/ffffff?text=Reliable+Fleet';"
            >
        </div>
    </section>

    <!-- Services Section (Light Green Background) --><section id="services" class="bg-light-bg py-16 md:py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <h3 class="text-3xl font-bold text-center text-primary-green mb-12">Our Core Services</h3>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">

                <!-- Service 1: Long-Haul --><div class="bg-white p-6 rounded-xl shadow-lg hover:shadow-xl transition duration-300 border-t-4 border-primary-green">
                    <div class="flex items-center text-dark-green mb-4">
                        <svg class="w-8 h-8 mr-3" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.828 0l-4.243-4.243a8 8 0 1111.314 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
                        <h4 class="text-xl font-semibold">Long-Haul Freight</h4>
                    </div>
                    <p class="text-gray-600">Our expertise is long-distance service, providing cross-country hauling with guaranteed on-time delivery across the entire U.S. We specialize in FTL (Full Truckload).</p>
                </div>

                <!-- Service 2: Local Delivery --><div class="bg-white p-6 rounded-xl shadow-lg hover:shadow-xl transition duration-300 border-t-4 border-primary-green">
                    <div class="flex items-center text-dark-green mb-4">
                        <svg class="w-8 h-8 mr-3" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"></path></svg>
                        <h4 class="text-xl font-semibold">Regional & Local</h4>
                    </div>
                    <p class="text-gray-600">Efficient and flexible transport solutions for short-to-medium distances within the greater metro area. Perfect for just-in-time logistics.</p>
                </div>

                <!-- Service 3: Specialized Freight --><div class="bg-white p-6 rounded-xl shadow-lg hover:shadow-xl transition duration-300 border-t-4 border-primary-green">
                    <div class="flex items-center text-dark-green mb-4">
                        <svg class="w-8 h-8 mr-3" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 13h6m-3-3v6m-9 1V7a2 2 0 012-2h6l2 2h6a2 2 0 012 2v8a2 2 0 01-2 2H5a2 2 0 01-2-2z"></path></svg>
                        <h4 class="text-xl font-semibold">Specialized Hauling</h4>
                    </div>
                    <p class="text-gray-600">Handling sensitive or unique cargo, including refrigerated goods (Reefer) and over-dimensional loads. Safety is our top priority.</p>
                </div>

            </div>
        </div>
    </section>

    <!-- Why Choose Us Section (White background) --><section id="about" class="bg-white py-16 md:py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="md:flex md:items-center md:space-x-12">
                <div class="md:w-1/2 mb-8 md:mb-0">
                    <img src="https://placehold.co/600x400/d1fae5/064e3b?text=Safety+First"
                         alt="Team member shaking hands"
                         class="w-full rounded-2xl shadow-xl object-cover h-64 md:h-96"
                         onerror="this.onerror=null;this.src='https://placehold.co/600x400/d1fae5/064e3b?text=Safety+First';"
                    >
                </div>
                <div class="md:w-1/2">
                    <span class="text-primary-green uppercase font-semibold text-sm tracking-widest">Our Unbeatable Edge</span>
                    <h3 class="text-4xl font-extrabold text-dark-green mt-2 mb-6">Why PRVT TRANSPORT is Your Best Logistics Partner</h3>
                    <p class="text-lg text-gray-700 mb-6">
                        Choosing a carrier is about trust, and PRVT TRANSPORT is built on a foundation of **guaranteed reliability and transparency**. We don't just move freight; we deliver peace of mind. We are the best choice because we commit to three core principles that minimize your risk and maximize your business efficiency:
                    </p>
                    <ul class="space-y-4 text-lg text-gray-700">
                        <li class="flex items-start">
                            <svg class="w-6 h-6 text-primary-green mr-3 mt-1 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.24a2 2 0 010 2.828L11.828 15a4 4 0 11-5.656-5.656l.828-.828"></path></svg>
                            <div>
                                <span class="font-bold text-dark-green">100% On-Time Reliability:</span> We guarantee scheduled pickup and delivery times. Our logistics systems are designed for **maximum uptime**, meaning fewer delays and more predictable supply chains for you.
                            </div>
                        </li>
                        <li class="flex items-start">
                            <svg class="w-6 h-6 text-primary-green mr-3 mt-1 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8a7 7 0 100 14A7 7 0 0012 8z"></path></svg>
                            <div>
                                <span class="font-bold text-dark-green">Advanced Fleet & Safety Record:</span> Our late-model trucks are meticulously maintained and equipped with the latest **real-time GPS tracking and safety technology**. Your cargo is secured by highly vetted, professionally trained drivers.
                            </div>
                        </li>
                        <li class="flex items-start">
                            <svg class="w-6 h-6 text-primary-green mr-3 mt-1 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-2.239 3-5s-1.343-5-3-5m0 10v-5m0 0h.01"></path></svg>
                            <div>
                                <span class="font-bold text-dark-green">24/7 Proactive Communication:</span> Our dedicated logistics experts are available around the clock. You get direct access to decision-makers and **proactive updates**, ensuring you're never left wondering about your freight's status.
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section (Light Green Background) --><section id="contact" class="bg-light-bg py-16 md:py-20">
        <div class="max-w-xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <h3 class="text-3xl font-bold text-dark-green mb-4">Ready to Get Rolling?</h3>
            <p class="text-lg text-gray-600 mb-8">
                Contact our logistics experts today for a custom freight solution and a transparent quote.
            </p>

            <div class="bg-white p-6 rounded-xl shadow-2xl border-t-4 border-primary-green text-left">
                <h4 class="text-xl font-bold text-primary-green mb-4">Get Your Free Quote</h4>
                
                <!-- START: Updated "Get in Touch" Block -->
                <p class="text-sm font-bold text-dark-green mb-3">Get in Touch:</p>
                
                <div class="space-y-3 mb-6">
                    <!-- Phone Number -->
                    <a href="tel:9084606880" class="flex items-center text-gray-700 hover:text-dark-green transition duration-200">
                        <svg class="w-5 h-5 text-dark-green mr-3 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path></svg>
                        (908) 460-6880
                    </a>
                    <!-- Email Link (Text changed to "Email Us") -->
                    <a href="mailto:Booking@prvttransport.com" class="flex items-center text-gray-700 hover:text-dark-green transition duration-200">
                        <svg class="w-5 h-5 text-dark-green mr-3 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8m-1 12H4a2 2 0 01-2-2V6a2 2 0 012-2h16a2 2 0 012 2v12a2 2 0 01-2 2z"></path></svg>
                        Email Us
                    </a>
                    <!-- Address -->
                    <p class="flex items-center text-gray-700">
                        <svg class="w-5 h-5 text-dark-green mr-3 flex-shrink-0" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.828 0l-4.243-4.243a8 8 0 1111.314 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
                        2 Arnot st , Lodi ,NJ 07644
                    </p>
                </div>
                <!-- END: Updated "Get in Touch" Block -->

                <!-- BEGIN QUOTE FORM --><form id="quote-form" class="mt-8 space-y-4">
                    <input type="text" id="fullName" placeholder="Full Name" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-primary-green focus:border-primary-green" required>
                    <input type="text" id="pickupAddress" placeholder="Pickup Address (City, State, Zip)" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-primary-green focus:border-primary-green" required>
                    <input type="text" id="dropoffAddress" placeholder="Drop-off Address (City, State, Zip)" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-primary-green focus:border-primary-green" required>
                    
                    <!-- Cargo Type Selection --><select id="cargoType" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-primary-green focus:border-primary-green" required>
                        <option value="" disabled selected>Select Cargo / Freight Type *</option>
                        <option value="general">General Dry Freight (Boxes, Pallets, etc.)</option>
                        <option value="reefer">Refrigerated / Temperature Controlled</option>
                        <option value="flatbed">Flatbed Cargo / Construction Materials</option>
                        <option value="hazmat">Hazardous Materials (Hazmat)</option>
                        <option value="other">Other / Specialized</option>
                    </select>

                    <!-- Truck/Trailer Size Selection --><select id="truckType" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-primary-green focus:border-primary-green" required>
                        <option value="" disabled selected>Select Required Truck / Trailer Type *</option>
                        <option value="53dry">53' Dry Van</option>
                        <option value="48dry">48' Dry Van</option>
                        <option value="flatbed">Flatbed Trailer</option>
                        <option value="reefer">Reefer Trailer (Refrigerated)</option>
                        <option value="straight">Straight Truck (Box Truck)</option>
                    </select>

                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                        <input type="tel" id="phoneNumber" placeholder="Phone Number" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-primary-green focus:border-primary-green" required>
                        <input type="email" id="emailAddress" placeholder="Email Address" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-primary-green focus:border-primary-green" required>
                    </div>

                    <label for="pickupDate" class="block text-sm font-medium text-gray-700 mt-2 text-left">Preferred Pickup Date</label>
                    <input type="date" id="pickupDate" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-primary-green focus:border-primary-green" required>

                    <select id="deliveryOption" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-primary-green focus:border-primary-green" required>
                        <option value="" disabled selected>Select Delivery Option</option>
                        <option value="standard">Standard Delivery</option>
                        <option value="rushed">Rushed/Expedited Delivery</option>
                    </select>

                    <textarea id="cargoDescription" placeholder="Describe your cargo (size, weight, special needs)" rows="3" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-primary-green focus:border-primary-green"></textarea>

                    <button type="submit" id="submit-button" class="w-full px-6 py-3 bg-dark-green text-white font-bold rounded-lg hover:bg-primary-green transition duration-300 transform hover:scale-[1.01]">
                        Submit Quote Request
                    </button>
                    <div id="form-message" class="mt-3 text-center font-semibold hidden"></div>
                </form>
                <!-- END QUOTE FORM --></div>
        </div>
    </section>

    <!-- Footer --><footer class="bg-primary-green text-white py-6">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center text-sm">
            &copy; <span id="currentYear"></span> PRVT TRANSPORT. All rights reserved.
        </div>
    </footer>
    
    <!-- ADMIN MODAL -->
    <div id="admin-modal" class="fixed inset-0 hidden items-center justify-center z-50 modal-overlay">
        <div class="bg-white w-11/12 md:w-4/5 max-w-5xl max-h-[95vh] rounded-xl shadow-2xl p-6 md:p-8 overflow-y-auto transform transition-all duration-300">
            <div id="admin-header" class="flex justify-between items-center border-b pb-4 mb-4">
                <h2 class="text-3xl font-bold text-dark-green" id="admin-title">Admin Dashboard: Quote Requests</h2>
                <button onclick="closeAdminModal()" class="text-gray-500 hover:text-red-600">
                    <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
                </button>
            </div>
            
            <div id="auth-status" class="text-center mb-4 p-3 rounded-lg bg-yellow-100 text-yellow-800 font-medium">
                Loading authentication status...
            </div>
            
            <div id="admin-content-wrapper">
                
                <!-- LIST VIEW -->
                <div id="list-view-container">
                    <p class="text-gray-600 mb-4">All client quote requests submitted through the form are listed below in real-time.</p>
                    <div id="quotes-list" class="space-y-4">
                        <p class="text-center text-gray-500" id="loading-quotes-message">Loading quotes...</p>
                        <!-- Quotes will be inserted here -->
                    </div>
                </div>

                <!-- SHIPMENT DETAIL/EDIT VIEW -->
                <div id="detail-view-container" class="hidden">
                    <button onclick="showListView()" class="mb-4 text-primary-green hover:text-dark-green font-semibold flex items-center">
                        <svg class="w-4 h-4 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 19l-7-7m0 0l7-7m-7 7h18"></path></svg>
                        Back to All Quotes
                    </button>
                    <form id="edit-shipment-form" class="bg-light-bg p-6 rounded-xl shadow-inner">
                        <input type="hidden" id="edit-shipment-id">
                        <h4 class="text-2xl font-bold text-dark-green mb-4">Manage Shipment: <span id="detail-client-name"></span></h4>

                        <!-- Tracking & Status -->
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
                            <div>
                                <label for="edit-status" class="block text-sm font-medium text-gray-700">Shipment Status</label>
                                <select id="edit-status" class="mt-1 w-full p-3 border border-gray-300 rounded-lg focus:ring-primary-green focus:border-primary-green font-bold">
                                    <option value="New">New Request</option>
                                    <option value="Quoted">Quoted</option>
                                    <option value="Booked">Booked (Confirmed)</option>
                                    <option value="In Transit">In Transit</option>
                                    <option value="Delivered">Delivered</option>
                                    <option value="Cancelled">Cancelled</option>
                                </select>
                            </div>
                            <div>
                                <label for="edit-driver" class="block text-sm font-medium text-gray-700">Assigned Driver</label>
                                <input type="text" id="edit-driver" placeholder="e.g., John Smith / Truck #45" class="mt-1 w-full p-3 border border-gray-300 rounded-lg focus:ring-primary-green focus:border-primary-green">
                            </div>
                        </div>

                        <!-- Internal Notes -->
                        <label for="edit-notes" class="block text-sm font-medium text-gray-700">Internal Tracking Notes</label>
                        <textarea id="edit-notes" rows="4" placeholder="Add tracking milestones, issues, or internal comments here." class="mt-1 w-full p-3 border border-gray-300 rounded-lg focus:ring-primary-green focus:border-primary-green"></textarea>

                        <div class="mt-6 border-t pt-4">
                            <h5 class="font-bold text-lg mb-2 text-primary-green">Original Quote Details</h5>
                            <div id="detail-quote-info" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-3 text-sm text-gray-700">
                                <!-- Detailed info injected here -->
                            </div>
                        </div>

                        <button type="submit" id="save-shipment-button" class="mt-8 w-full px-6 py-3 bg-primary-green text-white font-bold rounded-lg hover:bg-dark-green transition duration-300">
                            Save Shipment Changes and Update Status
                        </button>
                        <div id="save-message" class="mt-3 text-center font-semibold hidden"></div>
                    </form>
                </div>

            </div>
        </div>
    </div>

    <!-- Firebase SDK Imports and Logic --><script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getAuth, signInAnonymously, signInWithCustomToken, onAuthStateChanged, setPersistence, browserSessionPersistence } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getFirestore, collection, addDoc, onSnapshot, query, setLogLevel, serverTimestamp, updateDoc, doc, getDoc } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

        // Global variables provided by the environment
        const appId = typeof __app_id !== 'undefined' ? __app_id : 'default-app-id';
        const firebaseConfig = JSON.parse(typeof __firebase_config !== 'undefined' ? __firebase_config : '{}');
        const initialAuthToken = typeof __initial_auth_token !== 'undefined' ? __initial_auth_token : null;

        let db;
        let auth;
        let userId = null;
        let isAuthReady = false;
        let quotesMap = {}; 

        setLogLevel('Debug'); // Enable debug logging

        // Initialize Firebase
        const app = initializeApp(firebaseConfig);
        db = getFirestore(app);
        auth = getAuth(app);

        // DOM Elements
        const authStatusEl = document.getElementById('auth-status');
        const quotesListEl = document.getElementById('quotes-list');
        const formMessageEl = document.getElementById('form-message');
        const quoteFormEl = document.getElementById('quote-form');
        const adminModal = document.getElementById('admin-modal');
        const listContainer = document.getElementById('list-view-container');
        const detailContainer = document.getElementById('detail-view-container');
        const adminTitle = document.getElementById('admin-title');
        const saveMessageEl = document.getElementById('save-message');
        const editFormEl = document.getElementById('edit-shipment-form');
        const mobileMenuContent = document.getElementById('mobile-menu-content');


        const QUOTES_COLLECTION_PATH = `artifacts/${appId}/public/data/quotes`;

        /**
         * 1. Authentication Setup
         */
        onAuthStateChanged(auth, async (user) => {
            if (user) {
                userId = user.uid;
                authStatusEl.textContent = `Authenticated (UID: ${userId.substring(0, 8)}...)`;
                authStatusEl.className = 'text-center mb-4 p-3 rounded-lg bg-green-100 text-dark-green font-medium';
                isAuthReady = true;
                loadQuotes(); 
            } else {
                authStatusEl.textContent = 'Awaiting initial sign-in...';
                try {
                    await setPersistence(auth, browserSessionPersistence);
                    if (initialAuthToken) {
                        await signInWithCustomToken(auth, initialAuthToken);
                    } else {
                        await signInAnonymously(auth);
                    }
                } catch (error) {
                    console.error("Authentication failed:", error);
                    authStatusEl.textContent = `Authentication Failed. Error: ${error.message}`;
                    authStatusEl.className = 'text-center mb-4 p-3 rounded-lg bg-red-100 text-red-800 font-medium';
                }
            }
        });

        /**
         * 2. Quote Submission
         */
        quoteFormEl.addEventListener('submit', async (e) => {
            e.preventDefault();
            
            const submitButton = document.getElementById('submit-button');
            submitButton.disabled = true;
            submitButton.textContent = 'Sending Request...';
            formMessageEl.classList.add('hidden');

            const quoteData = {
                fullName: document.getElementById('fullName').value,
                pickupAddress: document.getElementById('pickupAddress').value,
                dropoffAddress: document.getElementById('dropoffAddress').value,
                phoneNumber: document.getElementById('phoneNumber').value,
                emailAddress: document.getElementById('emailAddress').value,
                pickupDate: document.getElementById('pickupDate').value,
                deliveryOption: document.getElementById('deliveryOption').value,
                cargoType: document.getElementById('cargoType').value,
                truckType: document.getElementById('truckType').value,
                cargoDescription: document.getElementById('cargoDescription').value,
                status: 'New', 
                driver: '', 
                internalNotes: '', 
                createdAt: serverTimestamp(),
                submittedBy: userId || 'anonymous',
            };

            try {
                if (!isAuthReady) {
                    throw new Error("System not ready. Please wait for authentication to complete.");
                }
                
                const docRef = await addDoc(collection(db, QUOTES_COLLECTION_PATH), quoteData);
                const quoteId = docRef.id;

                formMessageEl.innerHTML = `
                    ✅ Success! Your quote request has been submitted. 
                    <br>Your **Quote ID** is: <code class="font-mono text-xs bg-gray-200 p-1 rounded">${quoteId}</code>. 
                    
                `;
                formMessageEl.className = 'mt-3 text-center font-semibold p-2 rounded-lg bg-green-50 text-dark-green';
                quoteFormEl.reset();
            } catch (error) {
                console.error("Error submitting quote:", error);
                formMessageEl.textContent = `❌ Error submitting request: ${error.message}.`;
                formMessageEl.className = 'mt-3 text-center font-semibold p-2 rounded-lg bg-red-50 text-red-800';
            } finally {
                formMessageEl.classList.remove('hidden');
                submitButton.disabled = false;
                submitButton.textContent = 'Submit Quote Request';
            }
        });


        /**
         * 3. Admin Dashboard (Read/Real-time & Update)
         */
        function loadQuotes() {
            if (!isAuthReady) return;
            
            // NOTE: Firestore limits us from using orderBy() on non-indexed fields. 
            // We'll rely on client-side sorting if needed, but for real-time list view, 
            // a simple query is safest without specific instructions for indexes.
            const q = query(collection(db, QUOTES_COLLECTION_PATH)); 
            
            onSnapshot(q, (snapshot) => {
                quotesListEl.innerHTML = '';
                document.getElementById('loading-quotes-message').style.display = 'none';
                quotesMap = {}; 

                if (snapshot.empty) {
                    quotesListEl.innerHTML = '<p class="text-center text-gray-500 p-4 border rounded-lg">No quote requests submitted yet.</p>';
                    return;
                }
                
                // Client-side sorting by creation time (descending)
                const sortedDocs = snapshot.docs.sort((a, b) => {
                    const timeA = a.data().createdAt?.seconds || 0;
                    const timeB = b.data().createdAt?.seconds || 0;
                    return timeB - timeA; 
                });

                sortedDocs.forEach(doc => {
                    const quote = doc.data();
                    const quoteId = doc.id;
                    quotesMap[quoteId] = quote; 
                    
                    const item = document.createElement('div');
                    item.className = 'bg-white p-4 border border-gray-200 rounded-xl shadow-md hover:shadow-lg transition duration-200';
                    item.innerHTML = `
                        <div class="flex justify-between items-start border-b pb-2 mb-2">
                            <div>
                                <h5 class="text-lg font-bold text-dark-green">${quote.fullName || 'No Name Provided'}</h5>
                                <p class="text-xs text-gray-500">
                                    Full Quote ID: 
                                    <code class="font-mono text-xs bg-gray-100 p-0.5 rounded">${quoteId}</code> 
                                </p>
                            </div>
                            <span class="status-pill status-${quote.status.replace(/\s/g, '-')}" >${quote.status}</span>
                        </div>
                        <p class="text-sm text-gray-700"><strong>Route:</strong> ${quote.pickupAddress} &rarr; ${quote.dropoffAddress}</p>
                        <p class="text-sm text-gray-700"><strong>Cargo:</strong> ${quote.cargoType} (${quote.truckType})</p>
                        <p class="text-sm mt-3 flex justify-end">
                             <button onclick="openShipmentDetail('${quoteId}')" class="px-3 py-1 bg-primary-green text-white rounded-lg hover:bg-dark-green transition duration-200 text-xs font-semibold">
                                Manage Shipment
                            </button>
                        </p>
                    `;
                    quotesListEl.appendChild(item);
                });
            }, (error) => {
                console.error("Error listening to quotes:", error);
                quotesListEl.innerHTML = `<p class="text-center text-red-500">Error loading data: ${error.message}</p>`;
            });
        }

        // Admin Detail View and Editing
        window.openShipmentDetail = function(quoteId) {
            const quote = quotesMap[quoteId];
            if (!quote) {
                console.error("Quote data not found for ID:", quoteId);
                return;
            }

            adminTitle.textContent = `Managing Shipment for ${quote.fullName}`;
            document.getElementById('edit-shipment-id').value = quoteId;
            document.getElementById('edit-status').value = quote.status || 'New';
            document.getElementById('edit-driver').value = quote.driver || '';
            document.getElementById('edit-notes').value = quote.internalNotes || '';
            document.getElementById('detail-client-name').textContent = quote.fullName;

            const detailInfoEl = document.getElementById('detail-quote-info');
            detailInfoEl.innerHTML = `
                <p><strong>Route:</strong> ${quote.pickupAddress} to ${quote.dropoffAddress}</p>
                <p><strong>Contact:</strong> ${quote.phoneNumber} / ${quote.emailAddress}</p>
                <p><strong>Pickup Date:</strong> ${quote.pickupDate} (${quote.deliveryOption})</p>
                <p><strong>Cargo Type:</strong> ${quote.cargoType}</p>
                <p><strong>Truck Type:</strong> ${quote.truckType}</p>
                <p class="col-span-full"><strong>Description:</strong> ${quote.cargoDescription || 'N/A'}</p>
            `;
            
            listContainer.classList.add('hidden');
            detailContainer.classList.remove('hidden');
            saveMessageEl.classList.add('hidden'); 
        }
        
        editFormEl.addEventListener('submit', async (e) => {
            e.preventDefault();
            
            const quoteId = document.getElementById('edit-shipment-id').value;
            const saveButton = document.getElementById('save-shipment-button');
            
            saveButton.disabled = true;
            saveButton.textContent = 'Saving...';
            saveMessageEl.classList.add('hidden');

            const updatedData = {
                status: document.getElementById('edit-status').value,
                driver: document.getElementById('edit-driver').value,
                internalNotes: document.getElementById('edit-notes').value,
                lastUpdated: serverTimestamp(),
                updatedBy: userId || 'admin',
            };

            try {
                const quoteRef = doc(db, QUOTES_COLLECTION_PATH, quoteId);
                await updateDoc(quoteRef, updatedData);

                saveMessageEl.textContent = "✅ Shipment updated successfully!";
                saveMessageEl.className = 'mt-3 text-center font-semibold p-2 rounded-lg bg-green-50 text-dark-green';
            } catch (error) {
                console.error("Error saving shipment:", error);
                saveMessageEl.textContent = `❌ Error saving changes: ${error.message}.`;
                saveMessageEl.className = 'mt-3 text-center font-semibold p-2 rounded-lg bg-red-50 text-red-800';
            } finally {
                saveButton.disabled = false;
                saveButton.textContent = 'Save Shipment Changes and Update Status';
                saveMessageEl.classList.remove('hidden');
            }
        });

        window.showListView = function() {
            adminTitle.textContent = 'Admin Dashboard: Quote Requests';
            detailContainer.classList.add('hidden');
            listContainer.classList.remove('hidden');
        }


        /**
         * 4. Modal and Mobile Menu Functions
         */
        window.openAdminModal = function() {
            adminModal.classList.remove('hidden');
            adminModal.classList.add('flex');
            showListView();
        }

        window.closeAdminModal = function() {
            adminModal.classList.add('hidden');
            adminModal.classList.remove('flex');
        }
        
        window.toggleMobileMenu = function() {
            if (mobileMenuContent.classList.contains('hidden')) {
                mobileMenuContent.classList.remove('hidden');
            } else {
                mobileMenuContent.classList.add('hidden');
            }
        }

        // Set the current year in the footer
        document.getElementById('currentYear').textContent = new Date().getFullYear();
    </script>
</body>
</html>

