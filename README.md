# Travel
<!DOCTYPE html>
<html lang="vi">
<head>
    <base target="_self">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vietnam Travel Guide - Khám phá vẻ đẹp Việt Nam</title>
    <meta name="description" content="Khám phá các điểm du lịch tuyệt vời tại Việt Nam với đánh giá từ du khách, đặt tour và tư vấn trực tiếp">
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:wght@400;500;600;700&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        "primary": "#1a56db",
                        "secondary": "#059669",
                        "accent": "#dc2626",
                        "light": "#f8fafc",
                        "dark": "#0f172a"
                    },
                    fontFamily: {
                        "sans": ["Inter", "system-ui", "sans-serif"],
                        "serif": ["Playfair Display", "serif"]
                    },
                    backgroundImage: {
                        "hero-pattern": "url('https://picsum.photos/1920/1080?random=1')",
                        "feature-1": "url('https://picsum.photos/600/400?random=2')",
                        "feature-2": "url('https://picsum.photos/600/400?random=3')",
                        "feature-3": "url('https://picsum.photos/600/400?random=4')"
                    }
                }
            }
        }
    </script>
    <style>
        .hero-bg {
            background-image: linear-gradient(rgba(15, 23, 42, 0.7), rgba(15, 23, 42, 0.5)), url('https://picsum.photos/1920/1080?random=1');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
        }
        .card-hover {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .card-hover:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }
        .chatbot-toggle {
            animation: pulse 2s infinite;
        }
        @keyframes pulse {
            0%, 100% { box-shadow: 0 0 0 0 rgba(220, 38, 38, 0.7); }
            50% { box-shadow: 0 0 0 10px rgba(220, 38, 38, 0); }
        }
    </style>
</head>
<body class="font-sans text-gray-800 bg-light">
    <!-- Header & Navigation -->
    <header class="sticky top-0 z-50 bg-white shadow-md">
        <nav class="container mx-auto px-4 py-4">
            <div class="flex justify-between items-center">
                <div class="flex items-center space-x-2">
                    <div class="w-10 h-10 bg-primary rounded-full flex items-center justify-center">
                        <i class="fas fa-mountain text-white text-xl"></i>
                    </div>
                    <h1 class="text-2xl font-bold text-dark">Vietnam<span class="text-primary">Travel</span></h1>
                </div>
                
                <div class="hidden md:flex space-x-8">
                    <ul id="nav-menu" class="flex space-x-8"></ul>
                    <button id="chat-toggle" class="bg-accent text-white px-6 py-2 rounded-full hover:bg-red-700 transition">
                        <i class="fas fa-comment-alt mr-2"></i>Chat ngay
                    </button>
                </div>
                
                <button id="mobile-menu-btn" class="md:hidden text-dark">
                    <i class="fas fa-bars text-2xl"></i>
                </button>
            </div>
            
            <!-- Mobile Menu -->
            <div id="mobile-menu" class="hidden md:hidden mt-4 pb-4">
                <ul id="mobile-nav-menu" class="space-y-4"></ul>
                <button class="w-full bg-accent text-white px-6 py-3 rounded-full hover:bg-red-700 transition mt-4">
                    <i class="fas fa-comment-alt mr-2"></i>Chat ngay
                </button>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero-bg text-white py-20 md:py-32">
        <div class="container mx-auto px-4 text-center">
            <h2 class="font-serif text-4xl md:text-6xl font-bold mb-6">Khám phá vẻ đẹp Việt Nam</h2>
            <p class="text-xl md:text-2xl mb-10 max-w-3xl mx-auto">Trải nghiệm những địa điểm du lịch tuyệt vời với hướng dẫn chi tiết và đánh giá từ du khách</p>
            <div class="flex flex-col md:flex-row gap-4 justify-center">
                <button id="explore-btn" class="bg-primary hover:bg-blue-700 text-white px-8 py-4 rounded-full text-lg font-semibold transition">
                    <i class="fas fa-compass mr-2"></i>Khám phá ngay
                </button>
                <button id="register-btn" class="bg-white text-dark hover:bg-gray-100 px-8 py-4 rounded-full text-lg font-semibold transition">
                    <i class="fas fa-user-plus mr-2"></i>Đăng ký tài khoản
                </button>
            </div>
        </div>
    </section>

    <!-- Destinations Section -->
    <section class="py-16 bg-white">
        <div class="container mx-auto px-4">
            <div class="text-center mb-12">
                <h2 class="font-serif text-3xl md:text-4xl font-bold text-dark mb-4">Điểm đến nổi bật</h2>
                <p class="text-gray-600 max-w-2xl mx-auto">Khám phá những địa điểm du lịch hấp dẫn nhất Việt Nam với thông tin chi tiết và đánh giá từ du khách</p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-12">
                <div id="destinations-container"></div>
            </div>
            
            <div class="text-center">
                <button id="view-all-btn" class="border-2 border-primary text-primary hover:bg-primary hover:text-white px-8 py-3 rounded-full font-semibold transition">
                    Xem tất cả điểm đến <i class="fas fa-arrow-right ml-2"></i>
                </button>
            </div>
        </div>
    </section>

    <!-- Reviews Section -->
    <section class="py-16 bg-gray-50">
        <div class="container mx-auto px-4">
            <div class="text-center mb-12">
                <h2 class="font-serif text-3xl md:text-4xl font-bold text-dark mb-4">Đánh giá từ du khách</h2>
                <p class="text-gray-600 max-w-2xl mx-auto">Những trải nghiệm thực tế từ khách du lịch đã sử dụng dịch vụ của chúng tôi</p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <div id="reviews-container"></div>
            </div>
        </div>
    </section>

    <!-- Registration Section -->
    <section class="py-16 bg-gradient-to-r from-primary to-secondary">
        <div class="container mx-auto px-4">
            <div class="max-w-3xl mx-auto bg-white rounded-2xl shadow-xl p-8 md:p-12">
                <h2 class="font-serif text-3xl font-bold text-dark mb-6 text-center">Đăng ký nhận ưu đãi</h2>
                <p class="text-gray-600 mb-8 text-center">Đăng ký ngay để nhận thông tin tour mới nhất và ưu đãi đặc biệt</p>
                
                <form id="registration-form" class="space-y-6">
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <label class="block text-gray-700 mb-2">Họ và tên *</label>
                            <input type="text" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary">
                        </div>
                        <div>
                            <label class="block text-gray-700 mb-2">Email *</label>
                            <input type="email" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary">
                        </div>
                    </div>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div>
                            <label class="block text-gray-700 mb-2">Số điện thoại</label>
                            <input type="tel" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary">
                        </div>
                        <div>
                            <label class="block text-gray-700 mb-2">Điểm đến quan tâm</label>
                            <select class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary">
                                <option value="">Chọn điểm đến</option>
                                <option value="hanoi">Hà Nội</option>
                                <option value="danang">Đà Nẵng</option>
                                <option value="hoian">Hội An</option>
                                <option value="nhatrang">Nha Trang</option>
                                <option value="dalat">Đà Lạt</option>
                                <option value="phuquoc">Phú Quốc</option>
                            </select>
                        </div>
                    </div>
                    
                    <div>
                        <label class="block text-gray-700 mb-2">Lời nhắn</label>
                        <textarea rows="4" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary" placeholder="Bạn muốn tìm hiểu thêm về điều gì?"></textarea>
                    </div>
                    
                    <div class="flex items-center">
                        <input type="checkbox" id="newsletter" class="h-5 w-5 text-primary rounded">
                        <label for="newsletter" class="ml-3 text-gray-700">Tôi muốn nhận bản tin và ưu đãi qua email</label>
                    </div>
                    
                    <button type="submit" class="w-full bg-primary hover:bg-blue-700 text-white py-4 rounded-lg font-semibold text-lg transition">
                        <i class="fas fa-paper-plane mr-2"></i>Đăng ký ngay
                    </button>
                </form>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="py-16 bg-white">
        <div class="container mx-auto px-4">
            <div class="text-center mb-12">
                <h2 class="font-serif text-3xl md:text-4xl font-bold text-dark mb-4">Dịch vụ của chúng tôi</h2>
                <p class="text-gray-600 max-w-2xl mx-auto">Cung cấp đầy đủ các dịch vụ hỗ trợ cho chuyến du lịch hoàn hảo của bạn</p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div id="features-container"></div>
            </div>
        </div>
    </section>

    <!-- Chatbot Widget -->
    <div id="chatbot-widget" class="fixed bottom-6 right-6 z-40 hidden">
        <div class="bg-white rounded-2xl shadow-2xl w-80 md:w-96">
            <div class="bg-primary text-white p-4 rounded-t-2xl flex justify-between items-center">
                <h3 class="font-semibold text-lg"><i class="fas fa-robot mr-2"></i>Trợ lý du lịch</h3>
                <button id="close-chat" class="text-white hover:text-gray-200">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <div class="p-4 h-96 overflow-y-auto">
                <div class="mb-4">
                    <div class="bg-gray-100 rounded-lg p-3 max-w-xs">
                        <p class="text-sm">Xin chào! Tôi có thể giúp gì cho chuyến du lịch Việt Nam của bạn?</p>
                    </div>
                </div>
                
                <div class="space-y-3">
                    <button class="quick-question" data-question="Tour Hà Nội có gì hấp dẫn?">
                        <i class="fas fa-map-marker-alt mr-2"></i>Tour Hà Nội có gì hấp dẫn?
                    </button>
                    <button class="quick-question" data-question="Thời tiết Đà Nẵng tháng này thế nào?">
                        <i class="fas fa-cloud-sun mr-2"></i>Thời tiết Đà Nẵng tháng này thế nào?
                    </button>
                    <button class="quick-question" data-question="Cần chuẩn bị gì cho tour Sapa?">
                        <i class="fas fa-suitcase mr-2"></i>Cần chuẩn bị gì cho tour Sapa?
                    </button>
                    <button class="quick-question" data-question="Ưu đãi đặc biệt tháng này?">
                        <i class="fas fa-gift mr-2"></i>Ưu đãi đặc biệt tháng này?
                    </button>
                </div>
                
                <div class="mt-6">
                    <div class="flex">
                        <input type="text" id="chat-input" placeholder="Nhập câu hỏi của bạn..." class="flex-grow border border-gray-300 rounded-l-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-primary">
                        <button id="send-chat" class="bg-primary text-white px-4 py-2 rounded-r-lg hover:bg-blue-700">
                            <i class="fas fa-paper-plane"></i>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Chat Toggle Button -->
    <button id="chatbot-toggle-btn" class="fixed bottom-6 right-6 z-50 bg-accent text-white w-14 h-14 rounded-full shadow-lg chatbot-toggle flex items-center justify-center">
        <i class="fas fa-comment-alt text-2xl"></i>
    </button>

    <!-- Footer -->
    <footer class="bg-dark text-white pt-12 pb-8">
        <div class="container mx-auto px-4">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 mb-12">
                <div>
                    <div class="flex items-center space-x-2 mb-6">
                        <div class="w-10 h-10 bg-primary rounded-full flex items-center justify-center">
                            <i class="fas fa-mountain text-white text-xl"></i>
                        </div>
                        <h3 class="text-2xl font-bold">Vietnam<span class="text-primary">Travel</span></h3>
                    </div>
                    <p class="text-gray-300">Khám phá vẻ đẹp Việt Nam cùng chúng tôi. Trải nghiệm dịch vụ du lịch chất lượng với giá cả hợp lý.</p>
                </div>
                
                <div>
                    <h4 class="text-xl font-semibold mb-6">Liên kết nhanh</h4>
                    <ul id="footer-links-1" class="space-y-3"></ul>
                </div>
                
                <div>
                    <h4 class="text-xl font-semibold mb-6">Điểm đến</h4>
                    <ul id="footer-links-2" class="space-y-3"></ul>
                </div>
                
                <div>
                    <h4 class="text-xl font-semibold mb-6">Liên hệ</h4>
                    <ul class="space-y-3">
                        <li class="flex items-center">
                            <i class="fas fa-map-marker-alt text-primary mr-3"></i>
                            <span>123 Đường ABC, Quận 1, TP.HCM</span>
                        </li>
                        <li class="flex items-center">
                            <i class="fas fa-phone text-primary mr-3"></i>
                            <span>+84 123 456 789</span>
                        </li>
                        <li class="flex items-center">
                            <i class="fas fa-envelope text-primary mr-3"></i>
                            <span>info@vietnamtravel.com</span>
                        </li>
                    </ul>
                    
                    <div class="mt-6">
                        <h5 class="font-semibold mb-4">Kết nối với chúng tôi</h5>
                        <div class="flex space-x-4">
                            <a href="#" class="w-10 h-10 bg-gray-800 rounded-full flex items-center justify-center hover:bg-primary transition">
                                <i class="fab fa-facebook-f"></i>
                            </a>
                            <a href="#" class="w-10 h-10 bg-gray-800 rounded-full flex items-center justify-center hover:bg-primary transition">
                                <i class="fab fa-instagram"></i>
                            </a>
                            <a href="#" class="w-10 h-10 bg-gray-800 rounded-full flex items-center justify-center hover:bg-primary transition">
                                <i class="fab fa-youtube"></i>
                            </a>
                            <a href="#" class="w-10 h-10 bg-gray-800 rounded-full flex items-center justify-center hover:bg-primary transition">
                                <i class="fab fa-tiktok"></i>
                            </a>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="border-t border-gray-800 pt-8 text-center text-gray-400">
                <p>&copy; 2024 VietnamTravel. Tất cả các quyền được bảo lưu.</p>
            </div>
        </div>
    </footer>

    <script>
        // Data Layer
        const navigationItems = [
            { "label": "Trang chủ", "href": "#home", "icon": "fas fa-home" },
            { "label": "Điểm đến", "href": "#destinations", "icon": "fas fa-map-marker-alt" },
            { "label": "Đánh giá", "href": "#reviews", "icon": "fas fa-star" },
            { "label": "Dịch vụ", "href": "#services", "icon": "fas fa-concierge-bell" },
            { "label": "Liên hệ", "href": "#contact", "icon": "fas fa-phone" }
        ];

        const destinations = [
            { 
                "id": "hanoi",
                "name": "Hà Nội", 
                "description": "Thủ đô nghìn năm văn hiến với những di tích lịch sử và ẩm thực phong phú",
                "image": "https://picsum.photos/400/300?random=5",
                "rating": 4.8,
                "reviews": 1245,
                "price": "2.500.000 VND",
                "link": "#hanoi-detail"
            },
            { 
                "id": "hoian",
                "name": "Hội An", 
                "description": "Phố cổ di sản thế giới với kiến trúc cổ kính và đèn lồng rực rỡ",
                "image": "https://picsum.photos/400/300?random=6",
                "rating": 4.9,
                "reviews": 1890,
                "price": "3.200.000 VND",
                "link": "#hoian-detail"
            },
            { 
                "id": "dalat",
                "name": "Đà Lạt", 
                "description": "Thành phố ngàn hoa với khí hậu mát mẻ quanh năm và cảnh đẹp lãng mạn",
                "image": "https://picsum.photos/400/300?random=7",
                "rating": 4.7,
                "reviews": 987,
                "price": "2.800.000 VND",
                "link": "#dalat-detail"
            },
            { 
                "id": "nhatrang",
                "name": "Nha Trang", 
                "description": "Thiên đường biển với bãi cát trắng, nước trong xanh và resort sang trọng",
                "image": "https://picsum.photos/400/300?random=8",
                "rating": 4.6,
                "reviews": 1567,
                "price": "3.500.000 VND",
                "link": "#nhatrang-detail"
            },
            { 
                "id": "phuquoc",
                "name": "Phú Quốc", 
                "description": "Đảo ngọc với những bãi biển hoang sơ và hệ sinh thái rừng nguyên sinh",
                "image": "https://picsum.photos/400/300?random=9",
                "rating": 4.9,
                "reviews": 2103,
                "price": "4.500.000 VND",
                "link": "#phuquoc-detail"
            },
            { 
                "id": "sapa",
                "name": "Sa Pa", 
                "description": "Vùng núi hùng vĩ với ruộng bậc thang và văn hóa các dân tộc thiểu số",
                "image": "https://picsum.photos/400/300?random=10",
                "rating": 4.7,
                "reviews": 876,
                "price": "2.900.000 VND",
                "link": "#sapa-detail"
            }
        ];

        const reviews = [
            {
                "name": "Nguyễn Thị Mai",
                "avatar": "https://picsum.photos/100?random=11",
                "rating": 5,
                "destination": "Hội An",
                "comment": "Chuyến đi tuyệt vời! Hướng dẫn viên nhiệt tình, khách sạn đẹp, ẩm thực ngon. Sẽ quay lại vào năm sau!",
                "date": "15/03/2024"
            },
            {
                "name": "Trần Văn Nam",
                "avatar": "https://picsum.photos/100?random=12",
                "rating": 4,
                "destination": "Đà Lạt",
                "comment": "Cảnh đẹp, thời tiết mát mẻ. Tuy nhiên một số điểm tham quan hơi đông đúc. Dịch vụ tốt.",
                "date": "02/02/2024"
            },
            {
                "name": "Lê Hoàng Anh",
                "avatar": "https://picsum.photos/100?random=13",
                "rating": 5,
                "destination": "Phú Quốc",
                "comment": "Trải nghiệm tuyệt vời từ A đến Z. Biển đẹp, resort sang trọng, đồ ăn hải sản tươi ngon. Đáng đồng tiền!",
                "date": "28/01/2024"
            }
        ];

        const features = [
            {
                "icon": "fas fa-map-marked-alt",
                "title": "Tour đa dạng",
                "description": "Hơn 50 tour du lịch khắp Việt Nam với lịch trình chi tiết và giá cả hợp lý"
            },
            {
                "icon": "fas fa-headset",
                "title": "Hỗ trợ 24/7",
                "description": "Đội ngũ hỗ trợ khách hàng luôn sẵn sàng giải đáp mọi thắc mắc của bạn"
            },
            {
                "icon": "fas fa-shield-alt",
                "title": "Đảm bảo an toàn",
                "description": "Tuân thủ nghiêm ngặt các tiêu chuẩn an toàn và vệ sinh du lịch"
            }
        ];

        const footerLinks1 = [
            { "label": "Về chúng tôi", "href": "#about" },
            { "label": "Chính sách bảo mật", "href": "#privacy" },
            { "label": "Điều khoản dịch vụ", "href": "#terms" },
            { "label": "Câu hỏi thường gặp", "href": "#faq" }
        ];

        const footerLinks2 = [
            { "label": "Miền Bắc", "href": "#north" },
            { "label": "Miền Trung", "href": "#central" },
            { "label": "Miền Nam", "href": "#south" },
            { "label": "Tour đảo", "href": "#island" }
        ];

        // Render Functions
        function renderNavItems(items) {
            return items.map(item => 
                "<li><a href=\"" + item.href + "\" class=\"text-gray-700 hover:text-primary font-medium transition flex items-center\"><i class=\"" + item.icon + " mr-2\"></i>" + item.label + "</a></li>"
            ).join("");
        }

        function renderDestinations(items) {
            return items.map(item => `
                <div class="bg-white rounded-xl shadow-lg overflow-hidden card-hover">
                    <div class="relative">
                        <img src="${item.image}" alt="${item.name}" class="w-full h-48 object-cover" loading="lazy">
                        <div class="absolute top-4 right-4 bg-primary text-white px-3 py-1 rounded-full text-sm font-semibold">
                            ${item.price}
                        </div>
                    </div>
                    <div class="p-6">
                        <div class="flex justify-between items-start mb-3">
                            <h3 class="text-xl font-bold text-dark">${item.name}</h3>
                            <div class="flex items-center">
                                <i class="fas fa-star text-yellow-400 mr-1"></i>
                                <span class="font-semibold">${item.rating}</span>
                                <span class="text-gray-500 text-sm ml-1">(${item.reviews})</span>
                            </div>
                        </div>
                        <p class="text-gray-600 mb-4">${item.description}</p>
                        <div class="flex justify-between items-center">
                            <a href="${item.link}" class="text-primary hover:text-blue-700 font-semibold flex items-center">
                                Xem chi tiết <i class="fas fa-arrow-right ml-2"></i>
                            </a>
                            <button class="book-tour-btn bg-secondary hover:bg-green-700 text-white px-4 py-2 rounded-lg transition" data-destination="${item.id}">
                                <i class="fas fa-calendar-alt mr-2"></i>Đặt tour
                            </button>
                        </div>
                    </div>
                </div>
            `).join("");
        }

        function renderReviews(items) {
            return items.map(item => `
                <div class="bg-white rounded-xl shadow-lg p-6 card-hover">
                    <div class="flex items-center mb-4">
                        <img src="${item.avatar}" alt="${item.name}" class="w-12 h-12 rounded-full object-cover mr-4">
                        <div>
                            <h4 class="font-bold text-dark">${item.name}</h4>
                            <div class="flex items-center">
                                ${Array.from({length: 5}, (_, i) => 
                                    `<i class="fas fa-star ${i < item.rating ? 'text-yellow-400' : 'text-gray-300'}"></i>`
                                ).join('')}
                                <span class="text-gray-500 text-sm ml-2">${item.destination}</span>
                            </div>
                        </div>
                    </div>
                    <p class="text-gray-600 mb-4">"${item.comment}"</p>
                    <div class="text-gray-500 text-sm">${item.date}</div>
                </div>
            `).join("");
        }

        function renderFeatures(items) {
            return items.map(item => `
                <div class="text-center p-6 bg-gray-50 rounded-xl card-hover">
                    <div class="w-16 h-16 bg-primary rounded-full flex items-center justify-center mx-auto mb-6">
                        <i class="${item.icon} text-white text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold text-dark mb-4">${item.title}</h3>
                    <p class="text-gray-600">${item.description}</p>
                </div>
            `).join("");
        }

        function renderFooterLinks(items) {
            return items.map(item => 
                "<li><a href=\"" + item.href + "\" class=\"text-gray-300 hover:text-white transition\">" + item.label + "</a></li>"
            ).join("");
        }

        // Initialize Page
        document.addEventListener("DOMContentLoaded", function() {
            // Render navigation
            document.getElementById("nav-menu").innerHTML = renderNavItems(navigationItems);
            document.getElementById("mobile-nav-menu").innerHTML = renderNavItems(navigationItems);
            
            // Render destinations
            document.getElementById("destinations-container").innerHTML = renderDestinations(destinations);
            
            // Render reviews
            document.getElementById("reviews-container").innerHTML = renderReviews(reviews);
            
            // Render features
            document.getElementById("features-container").innerHTML = renderFeatures(features);
            
            // Render footer links
            document.getElementById("footer-links-1").innerHTML = renderFooterLinks(footerLinks1);
            document.getElementById("footer-links-2").innerHTML = renderFooterLinks(footerLinks2);
            
            // Mobile menu toggle
            const mobileMenuBtn = document.getElementById("mobile-menu-btn");
            const mobileMenu = document.getElementById("mobile-menu");
            
            mobileMenuBtn.addEventListener("click", function() {
                mobileMenu.classList.toggle("hidden");
                const icon = mobileMenuBtn.querySelector("i");
                if (mobileMenu.classList.contains("hidden")) {
                    icon.className = "fas fa-bars text-2xl";
                } else {
                    icon.className = "fas fa-times text-2xl";
                }
            });
            
            // Chatbot toggle
            const chatToggleBtn = document.getElementById("chatbot-toggle-btn");
            const chatWidget = document.getElementById("chatbot-widget");
            const closeChatBtn = document.getElementById("close-chat");
            const chatToggle = document.getElementById("chat-toggle");
            
            function toggleChat() {
                chatWidget.classList.toggle("hidden");
            }
            
            chatToggleBtn.addEventListener("click", toggleChat);
            if (chatToggle) chatToggle.addEventListener("click", toggleChat);
            closeChatBtn.addEventListener("click", toggleChat);
            
            // Quick question buttons
            document.querySelectorAll(".quick-question").forEach(button => {
                button.addEventListener("click", function() {
                    const question = this.getAttribute("data-question");
                    const chatInput = document.getElementById("chat-input");
                    chatInput.value = question;
                    chatInput.focus();
                });
            });
            
            // Send chat message
            document.getElementById("send-chat").addEventListener("click", function() {
                const chatInput = document.getElementById("chat-input");
                const message = chatInput.value.trim();
                
                if (message) {
                    // In a real implementation, this would send to a chatbot API
                    alert("Câu hỏi của bạn đã được gửi: \"" + message + "\"\nTrợ lý AI sẽ trả lời bạn trong giây lát!");
                    chatInput.value = "";
                }
            });
            
            // Book tour buttons
            document.querySelectorAll(".book-tour-btn").forEach(button => {
                button.addEventListener("click", function() {
                    const destination = this.getAttribute("data-destination");
                    const destName = destinations.find(d => d.id === destination)?.name || destination;
                    alert("Bạn đã chọn đặt tour " + destName + "!\nChúng tôi sẽ liên hệ với bạn trong thời gian sớm nhất.");
                });
            });
            
            // Registration form
            document.getElementById("registration-form").addEventListener("submit", function(e) {
                e.preventDefault();
                alert("Cảm ơn bạn đã đăng ký!\nChúng tôi sẽ gửi thông tin ưu đãi đến email của bạn.");
                this.reset();
            });
            
            // Explore button
            document.getElementById("explore-btn").addEventListener("click", function() {
                document.getElementById("destinations").scrollIntoView({ behavior: "smooth" });
            });
            
            // View all destinations
            document.getElementById("view-all-btn").addEventListener("click", function() {
                alert("Đang tải tất cả điểm đến...\nTrang sẽ hiển thị đầy đủ 20+ điểm đến du lịch tại Việt Nam!");
            });
            
            // Register button
            document.getElementById("register-btn").addEventListener("click", function() {
                document.querySelector("section.py-16.bg-gradient-to-r").scrollIntoView({ behavior: "smooth" });
            });
            
            // Smooth scrolling for anchor links
            document.addEventListener("click", function(e) {
                if (e.target.tagName === "A" && e.target.getAttribute("href")?.startsWith("#")) {
                    e.preventDefault();
                    const targetId = e.target.getAttribute("href");
                    const targetElement = document.querySelector(targetId);
                    if (targetElement) {
                        targetElement.scrollIntoView({ behavior: "smooth", block: "start" });
                    }
                }
            });
        });
    </script>
</body>
</html>
