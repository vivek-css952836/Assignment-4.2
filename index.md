<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Job Application Form - Assignment 4.2</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                }
            }
        }
    </script>
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
    </style>
</head>
<body class="bg-slate-100 min-h-screen py-8 px-4 flex flex-col justify-center items-center">

    <!-- Container Card -->
    <div class="max-w-3xl w-full bg-white rounded-2xl shadow-xl overflow-hidden my-6 border border-slate-200">
        
        <!-- Header Banner -->
        <div class="bg-indigo-600 px-8 py-6 text-white">
            <h1 class="text-3xl font-bold">Job Application Form</h1>
            <p class="text-indigo-200 text-sm mt-1">Please fill out the form below to apply for your desired position.</p>
        </div>

        <!-- Submission Alert Banner (Hidden by default) -->
        <div id="successBanner" class="hidden bg-emerald-50 border-l-4 border-emerald-500 p-4 m-8 mb-0 rounded-r text-emerald-800">
            <div class="flex items-center">
                <i class="fa-solid fa-circle-check text-xl mr-3 text-emerald-500"></i>
                <div>
                    <p class="font-bold">Application Submitted Successfully!</p>
                    <p class="text-sm text-emerald-700">Thank you for applying. We will review your profile and contact you soon.</p>
                </div>
            </div>
        </div>

        <!-- Form Body -->
        <form id="jobAppForm" class="p-8 space-y-6" onsubmit="handleFormSubmit(event)">

            <!-- Section 1: System Info (Disabled Example) -->
            <div class="bg-slate-50 p-4 rounded-xl border border-slate-200">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <!-- Disabled Field 1: Application Ref ID -->
                    <div>
                        <label for="appRefNumber" class="block text-xs font-semibold uppercase tracking-wider text-slate-500 mb-1">
                            Application Reference No. <span class="text-xs text-slate-400">(Auto-generated / Disabled)</span>
                        </label>
                        <input 
                            type="text" 
                            id="appRefNumber" 
                            name="appRefNumber" 
                            value="APP-2026-89412" 
                            disabled 
                            class="w-full bg-slate-200 text-slate-600 border border-slate-300 rounded-lg px-3 py-2 text-sm cursor-not-allowed font-mono shadow-inner"
                        />
                    </div>
                    <!-- Disabled Field 2: Application Status -->
                    <div>
                        <label for="appStatus" class="block text-xs font-semibold uppercase tracking-wider text-slate-500 mb-1">
                            Application Status <span class="text-xs text-slate-400">(Disabled)</span>
                        </label>
                        <input 
                            type="text" 
                            id="appStatus" 
                            name="appStatus" 
                            value="Draft Mode" 
                            disabled 
                            class="w-full bg-slate-200 text-slate-600 border border-slate-300 rounded-lg px-3 py-2 text-sm cursor-not-allowed font-medium shadow-inner"
                        />
                    </div>
                </div>
            </div>

            <!-- Section 2: Personal & Contact Information -->
            <div>
                <h2 class="text-lg font-semibold text-slate-800 border-b pb-2 mb-4">Personal Details</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    
                    <!-- 1. Full Name -->
                    <div class="md:col-span-2">
                        <label for="fullName" class="block text-sm font-medium text-slate-700 mb-1">
                            Full Name <span class="text-red-500">*</span>
                        </label>
                        <input 
                            type="text" 
                            id="fullName" 
                            name="fullName" 
                            placeholder="e.g. Jane Doe" 
                            required 
                            class="w-full px-4 py-2.5 rounded-lg border border-slate-300 focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500 outline-none transition text-slate-800 placeholder-slate-400"
                        />
                    </div>

                    <!-- 2. Email Address -->
                    <div>
                        <label for="email" class="block text-sm font-medium text-slate-700 mb-1">
                            Email Address <span class="text-red-500">*</span>
                        </label>
                        <input 
                            type="email" 
                            id="email" 
                            name="email" 
                            placeholder="jane.doe@example.com" 
                            required 
                            class="w-full px-4 py-2.5 rounded-lg border border-slate-300 focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500 outline-none transition text-slate-800 placeholder-slate-400"
                        />
                    </div>

                    <!-- 3. Phone Number -->
                    <div>
                        <label for="phone" class="block text-sm font-medium text-slate-700 mb-1">
                            Phone Number <span class="text-red-500">*</span>
                        </label>
                        <input 
                            type="tel" 
                            id="phone" 
                            name="phone" 
                            placeholder="+1 (555) 000-0000" 
                            required 
                            class="w-full px-4 py-2.5 rounded-lg border border-slate-300 focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500 outline-none transition text-slate-800 placeholder-slate-400"
                        />
                    </div>

                    <!-- 4. Date of Birth -->
                    <div>
                        <label for="dob" class="block text-sm font-medium text-slate-700 mb-1">
                            Date of Birth <span class="text-red-500">*</span>
                        </label>
                        <input 
                            type="date" 
                            id="dob" 
                            name="dob" 
                            required 
                            class="w-full px-4 py-2.5 rounded-lg border border-slate-300 focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500 outline-none transition text-slate-800"
                        />
                    </div>

                    <!-- 5. Portfolio URL -->
                    <div>
                        <label for="portfolioUrl" class="block text-sm font-medium text-slate-700 mb-1">
                            Portfolio URL
                        </label>
                        <input 
                            type="url" 
                            id="portfolioUrl" 
                            name="portfolioUrl" 
                            placeholder="https://myportfolio.com" 
                            class="w-full px-4 py-2.5 rounded-lg border border-slate-300 focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500 outline-none transition text-slate-800 placeholder-slate-400"
                        />
                    </div>

                </div>
            </div>

            <!-- Section 3: Preferences & Qualifications -->
            <div>
                <h2 class="text-lg font-semibold text-slate-800 border-b pb-2 mb-4">Position & Role Details</h2>
                <div class="space-y-6">

                    <!-- 6. Preferred Shift (Radio Buttons - Shared 'name' attribute) -->
                    <div>
                        <label class="block text-sm font-medium text-slate-700 mb-2">
                            Preferred Work Shift <span class="text-red-500">*</span>
                        </label>
                        <div class="flex flex-wrap gap-4">
                            <label class="flex items-center space-x-2 cursor-pointer bg-slate-50 border border-slate-200 px-4 py-2.5 rounded-lg hover:bg-slate-100 transition">
                                <input type="radio" id="shiftMorning" name="preferredShift" value="Morning" required class="text-indigo-600 focus:ring-indigo-500 h-4 w-4">
                                <span class="text-sm font-medium text-slate-700">Morning Shift</span>
                            </label>

                            <label class="flex items-center space-x-2 cursor-pointer bg-slate-50 border border-slate-200 px-4 py-2.5 rounded-lg hover:bg-slate-100 transition">
                                <input type="radio" id="shiftEvening" name="preferredShift" value="Evening" class="text-indigo-600 focus:ring-indigo-500 h-4 w-4">
                                <span class="text-sm font-medium text-slate-700">Evening Shift</span>
                            </label>

                            <label class="flex items-center space-x-2 cursor-pointer bg-slate-50 border border-slate-200 px-4 py-2.5 rounded-lg hover:bg-slate-100 transition">
                                <input type="radio" id="shiftNight" name="preferredShift" value="Night" class="text-indigo-600 focus:ring-indigo-500 h-4 w-4">
                                <span class="text-sm font-medium text-slate-700">Night Shift</span>
                            </label>
                            
                            <label class="flex items-center space-x-2 cursor-pointer bg-slate-50 border border-slate-200 px-4 py-2.5 rounded-lg hover:bg-slate-100 transition">
                                <input type="radio" id="shiftFlexible" name="preferredShift" value="Flexible" class="text-indigo-600 focus:ring-indigo-500 h-4 w-4">
                                <span class="text-sm font-medium text-slate-700">Flexible</span>
                            </label>
                        </div>
                    </div>

                    <!-- 8. Qualification or Job Role Dropdown -->
                    <div>
                        <label for="jobRole" class="block text-sm font-medium text-slate-700 mb-1">
                            Target Job Role <span class="text-red-500">*</span>
                        </label>
                        <select 
                            id="jobRole" 
                            name="jobRole" 
                            required 
                            class="w-full px-4 py-2.5 rounded-lg border border-slate-300 focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500 outline-none transition text-slate-800 bg-white"
                        >
                            <option value="" disabled selected>-- Select target job role --</option>
                            <option value="Frontend Developer">Frontend Developer</option>
                            <option value="Backend Developer">Backend Developer</option>
                            <option value="Full Stack Engineer">Full Stack Engineer</option>
                            <option value="UI/UX Designer">UI/UX Designer</option>
                            <option value="QA Engineer">QA Engineer</option>
                            <option value="Project Manager">Project Manager</option>
                        </select>
                    </div>

                    <!-- 7. Technical Skills (Checkboxes) -->
                    <div>
                        <label class="block text-sm font-medium text-slate-700 mb-2">
                            Key Skills <span class="text-slate-400 text-xs">(Select all that apply)</span>
                        </label>
                        <div class="grid grid-cols-2 sm:grid-cols-3 gap-3">
                            <label for="skillHtml" class="flex items-center space-x-2 cursor-pointer bg-slate-50 border border-slate-200 p-2.5 rounded-lg hover:bg-slate-100 transition">
                                <input type="checkbox" id="skillHtml" name="skills" value="HTML5" class="rounded text-indigo-600 focus:ring-indigo-500 h-4 w-4">
                                <span class="text-sm text-slate-700">HTML5</span>
                            </label>

                            <label for="skillCss" class="flex items-center space-x-2 cursor-pointer bg-slate-50 border border-slate-200 p-2.5 rounded-lg hover:bg-slate-100 transition">
                                <input type="checkbox" id="skillCss" name="skills" value="CSS3/Tailwind" class="rounded text-indigo-600 focus:ring-indigo-500 h-4 w-4">
                                <span class="text-sm text-slate-700">CSS3 / Tailwind</span>
                            </label>

                            <label for="skillJs" class="flex items-center space-x-2 cursor-pointer bg-slate-50 border border-slate-200 p-2.5 rounded-lg hover:bg-slate-100 transition">
                                <input type="checkbox" id="skillJs" name="skills" value="JavaScript" class="rounded text-indigo-600 focus:ring-indigo-500 h-4 w-4">
                                <span class="text-sm text-slate-700">JavaScript</span>
                            </label>

                            <label for="skillReact" class="flex items-center space-x-2 cursor-pointer bg-slate-50 border border-slate-200 p-2.5 rounded-lg hover:bg-slate-100 transition">
                                <input type="checkbox" id="skillReact" name="skills" value="React" class="rounded text-indigo-600 focus:ring-indigo-500 h-4 w-4">
                                <span class="text-sm text-slate-700">React</span>
                            </label>

                            <label for="skillNode" class="flex items-center space-x-2 cursor-pointer bg-slate-50 border border-slate-200 p-2.5 rounded-lg hover:bg-slate-100 transition">
                                <input type="checkbox" id="skillNode" name="skills" value="Node.js" class="rounded text-indigo-600 focus:ring-indigo-500 h-4 w-4">
                                <span class="text-sm text-slate-700">Node.js</span>
                            </label>

                            <label for="skillGit" class="flex items-center space-x-2 cursor-pointer bg-slate-50 border border-slate-200 p-2.5 rounded-lg hover:bg-slate-100 transition">
                                <input type="checkbox" id="skillGit" name="skills" value="Git" class="rounded text-indigo-600 focus:ring-indigo-500 h-4 w-4">
                                <span class="text-sm text-slate-700">Git / GitHub</span>
                            </label>
                        </div>
                    </div>

                    <!-- 9. Cover Letter (<textarea>) -->
                    <div>
                        <label for="coverLetter" class="block text-sm font-medium text-slate-700 mb-1">
                            Cover Letter
                        </label>
                        <textarea 
                            id="coverLetter" 
                            name="coverLetter" 
                            rows="5" 
                            placeholder="Tell us briefly about your experience, background, and why you are a great fit..." 
                            class="w-full px-4 py-2.5 rounded-lg border border-slate-300 focus:ring-2 focus:ring-indigo-500 focus:border-indigo-500 outline-none transition text-slate-800 placeholder-slate-400"
                        ></textarea>
                    </div>

                </div>
            </div>

            <!-- 10. Submit Button -->
            <div class="pt-4 flex flex-col sm:flex-row justify-end gap-3 border-t">
                <button 
                    type="reset" 
                    class="w-full sm:w-auto px-6 py-2.5 border border-slate-300 rounded-lg text-slate-700 font-medium hover:bg-slate-100 transition"
                >
                    Clear Form
                </button>
                <button 
                    type="submit" 
                    class="w-full sm:w-auto px-8 py-2.5 bg-indigo-600 text-white font-semibold rounded-lg shadow-md hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 transition"
                >
                    Submit Application
                </button>
            </div>

        </form>

        <!-- Card Footer -->
        <div class="bg-slate-50 px-8 py-4 border-t border-slate-200 text-center text-xs text-slate-500">
            Assignment 4.2 — Job Application Form | Responsive HTML5 & Tailwind CSS
        </div>

    </div>