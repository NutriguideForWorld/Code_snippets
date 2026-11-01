```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Frequently Asked Questions</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8fafc; /* slate-50 */
        }
        
        /* Hide the default marker for details/summary */
        details > summary {
            list-style: none;
        }
        details > summary::-webkit-details-marker {
            display: none;
        }
        
        /* Smooth icon rotation */
        summary svg {
            transition: transform 0.3s ease-in-out;
        }
        details[open] summary svg {
            transform: rotate(180deg);
        }

        /* Subtle fade in for content */
        details[open] summary ~ div {
            animation: fadeIn 0.4s ease-in-out;
        }

        @keyframes fadeIn {
            0% { opacity: 0; transform: translateY(-10px); }
            100% { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body class="text-slate-800 antialiased min-h-screen p-6 md:p-12">

    <div class="max-w-4xl mx-auto">
        
        <!-- Header -->
        <div class="text-center mb-12">
            <h1 class="text-3xl md:text-4xl font-bold text-slate-900 mb-4">Frequently Asked Questions</h1>
            <p class="text-slate-500 max-w-2xl mx-auto">Find answers to common questions about our manufacturing, shipping, branding, and warranty policies below.</p>
        </div>

        <div class="space-y-10">

            <!-- Category: Quality -->
            <section>
                <h2 class="text-xl font-bold text-indigo-600 mb-4 flex items-center border-b pb-2">
                    <svg class="w-6 h-6 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z"></path></svg>
                    Quality
                </h2>
                <div class="space-y-3">
                    
                    <details class="group bg-white border border-slate-200 rounded-lg shadow-sm overflow-hidden">
                        <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-5 hover:bg-slate-50 transition-colors">
                            <span>Can you provide food-safety and lead/cadmium test reports?</span>
                            <span class="transition group-open:rotate-180">
                                <svg fill="none" height="24" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="24"><path d="M6 9l6 6 6-6"></path></svg>
                            </span>
                        </summary>
                        <div class="p-5 pt-0 text-slate-500 leading-relaxed border-t border-slate-100 mt-2 text-sm">
                            Yes, we can provide comprehensive food-safety compliance certificates and detailed lead/cadmium test reports from internationally recognized third-party laboratories upon request.
                        </div>
                    </details>

                    <details class="group bg-white border border-slate-200 rounded-lg shadow-sm overflow-hidden">
                        <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-5 hover:bg-slate-50 transition-colors">
                            <span>What is your acceptable manufacturing defect percentage?</span>
                            <span class="transition group-open:rotate-180">
                                <svg fill="none" height="24" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="24"><path d="M6 9l6 6 6-6"></path></svg>
                            </span>
                        </summary>
                        <div class="p-5 pt-0 text-slate-500 leading-relaxed border-t border-slate-100 mt-2 text-sm">
                            Our standard acceptable manufacturing defect rate is strictly maintained below 2%. We have rigorous quality control processes in place to ensure you receive the highest quality products.
                        </div>
                    </details>

                    <details class="group bg-white border border-slate-200 rounded-lg shadow-sm overflow-hidden">
                        <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-5 hover:bg-slate-50 transition-colors">
                            <span>Can we conduct third-party inspection before dispatch?</span>
                            <span class="transition group-open:rotate-180">
                                <svg fill="none" height="24" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="24"><path d="M6 9l6 6 6-6"></path></svg>
                            </span>
                        </summary>
                        <div class="p-5 pt-0 text-slate-500 leading-relaxed border-t border-slate-100 mt-2 text-sm">
                            Absolutely. We welcome and can accommodate third-party inspections (such as SGS, Intertek, or your designated representatives) at our facility prior to final dispatch.
                        </div>
                    </details>

                </div>
            </section>

            <!-- Category: Warranty -->
            <section>
                <h2 class="text-xl font-bold text-indigo-600 mb-4 flex items-center border-b pb-2">
                    <svg class="w-6 h-6 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"></path></svg>
                    Warranty
                </h2>
                <div class="space-y-3">
                    
                    <details class="group bg-white border border-slate-200 rounded-lg shadow-sm overflow-hidden">
                        <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-5 hover:bg-slate-50 transition-colors">
                            <span>What is your replacement policy for manufacturing defects?</span>
                            <span class="transition group-open:rotate-180">
                                <svg fill="none" height="24" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="24"><path d="M6 9l6 6 6-6"></path></svg>
                            </span>
                        </summary>
                        <div class="p-5 pt-0 text-slate-500 leading-relaxed border-t border-slate-100 mt-2 text-sm">
                            If products are found to have manufacturing defects exceeding our agreed acceptable percentage upon arrival, we will provide direct replacements in your next shipment or offer equivalent compensation based on the claim investigation.
                        </div>
                    </details>

                    <details class="group bg-white border border-slate-200 rounded-lg shadow-sm overflow-hidden">
                        <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-5 hover:bg-slate-50 transition-colors">
                            <span>Do you compensate for damaged or missing quantities?</span>
                            <span class="transition group-open:rotate-180">
                                <svg fill="none" height="24" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="24"><path d="M6 9l6 6 6-6"></path></svg>
                            </span>
                        </summary>
                        <div class="p-5 pt-0 text-slate-500 leading-relaxed border-t border-slate-100 mt-2 text-sm">
                            Yes, claims for damages during transit (if shipped under our insurance terms) or short shipments must be submitted with photographic evidence within 14 days of receiving the container. Validated claims are fully compensated.
                        </div>
                    </details>

                    <details class="group bg-white border border-slate-200 rounded-lg shadow-sm overflow-hidden">
                        <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-5 hover:bg-slate-50 transition-colors">
                            <span>Can you provide credit notes for defective products?</span>
                            <span class="transition group-open:rotate-180">
                                <svg fill="none" height="24" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="24"><path d="M6 9l6 6 6-6"></path></svg>
                            </span>
                        </summary>
                        <div class="p-5 pt-0 text-slate-500 leading-relaxed border-t border-slate-100 mt-2 text-sm">
                            Yes, instead of replacement items, we can issue official credit notes for the value of verified defective products. This credit can be applied directly to your future purchase orders.
                        </div>
                    </details>

                </div>
            </section>

            <!-- Category: Shipment -->
            <section>
                <h2 class="text-xl font-bold text-indigo-600 mb-4 flex items-center border-b pb-2">
                    <svg class="w-6 h-6 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7h12m0 0l-4-4m4 4l-4 4m0 6H4m0 0l4 4m-4-4l4-4"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16V6a1 1 0 00-1-1H4a1 1 0 00-1 1v10a1 1 0 001 1h8a1 1 0 001-1z" opacity="0"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 17a2 2 0 11-4 0 2 2 0 014 0zM19 17a2 2 0 11-4 0 2 2 0 014 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16V6a1 1 0 00-1-1H4a1 1 0 00-1 1v10a1 1 0 001 1h8a1 1 0 001-1h3l3 3h-3"></path></svg>
                    Shipment
                </h2>
                <div class="space-y-3">
                    
                    <details class="group bg-white border border-slate-200 rounded-lg shadow-sm overflow-hidden">
                        <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-5 hover:bg-slate-50 transition-colors">
                            <span>What is the export packaging specification?</span>
                            <span class="transition group-open:rotate-180">
                                <svg fill="none" height="24" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="24"><path d="M6 9l6 6 6-6"></path></svg>
                            </span>
                        </summary>
                        <div class="p-5 pt-0 text-slate-500 leading-relaxed border-t border-slate-100 mt-2 text-sm">
                            Our standard export packaging involves individual items separated by corrugated dividers, placed inside heavy-duty 5-ply export master cartons. Palletization with shrink wrap and edge protectors can be arranged upon request.
                        </div>
                    </details>

                    <details class="group bg-white border border-slate-200 rounded-lg shadow-sm overflow-hidden">
                        <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-5 hover:bg-slate-50 transition-colors">
                            <span>How many pieces can fit in a 20-foot and 40-foot container?</span>
                            <span class="transition group-open:rotate-180">
                                <svg fill="none" height="24" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="24"><path d="M6 9l6 6 6-6"></path></svg>
                            </span>
                        </summary>
                        <div class="p-5 pt-0 text-slate-500 leading-relaxed border-t border-slate-100 mt-2 text-sm">
                            Container capacity varies heavily depending on the specific SKU dimensions and packaging style. Once you finalize your product selection, we will provide a precise packing list and CBM calculation to maximize container utilization.
                        </div>
                    </details>

                    <details class="group bg-white border border-slate-200 rounded-lg shadow-sm overflow-hidden">
                        <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-5 hover:bg-slate-50 transition-colors">
                            <span>Can multiple designs and SKUs be consolidated?</span>
                            <span class="transition group-open:rotate-180">
                                <svg fill="none" height="24" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="24"><path d="M6 9l6 6 6-6"></path></svg>
                            </span>
                        </summary>
                        <div class="p-5 pt-0 text-slate-500 leading-relaxed border-t border-slate-100 mt-2 text-sm">
                            Yes, we routinely consolidate multiple designs, colors, and SKUs into a single container shipment, provided each item meets its respective Minimum Order Quantity (MOQ).
                        </div>
                    </details>

                </div>
            </section>

            <!-- Category: Branding -->
            <section>
                <h2 class="text-xl font-bold text-indigo-600 mb-4 flex items-center border-b pb-2">
                    <svg class="w-6 h-6 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 7h.01M7 3h5c.512 0 1.024.195 1.414.586l7 7a2 2 0 010 2.828l-7 7a2 2 0 01-2.828 0l-7-7A1.994 1.994 0 013 12V7a4 4 0 014-4z"></path></svg>
                    Branding
                </h2>
                <div class="space-y-3">
                    
                    <details class="group bg-white border border-slate-200 rounded-lg shadow-sm overflow-hidden">
                        <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-5 hover:bg-slate-50 transition-colors">
                            <span>Can you print our logo on the plate?</span>
                            <span class="transition group-open:rotate-180">
                                <svg fill="none" height="24" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="24"><path d="M6 9l6 6 6-6"></path></svg>
                            </span>
                        </summary>
                        <div class="p-5 pt-0 text-slate-500 leading-relaxed border-t border-slate-100 mt-2 text-sm">
                            Yes, custom logo printing is a standard service we offer. We utilize high-durability decal firing or pad printing depending on the material, ensuring your logo is permanent and dishwasher safe.
                        </div>
                    </details>

                    <details class="group bg-white border border-slate-200 rounded-lg shadow-sm overflow-hidden">
                        <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-5 hover:bg-slate-50 transition-colors">
                            <span>What is the MOQ for private-label production?</span>
                            <span class="transition group-open:rotate-180">
                                <svg fill="none" height="24" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="24"><path d="M6 9l6 6 6-6"></path></svg>
                            </span>
                        </summary>
                        <div class="p-5 pt-0 text-slate-500 leading-relaxed border-t border-slate-100 mt-2 text-sm">
                            The Minimum Order Quantity (MOQ) for private-label production typically starts at 1,000 pieces per design, though this can vary slightly based on the complexity of the mold and printing requirements.
                        </div>
                    </details>

                    <details class="group bg-white border border-slate-200 rounded-lg shadow-sm overflow-hidden">
                        <summary class="flex justify-between items-center font-medium cursor-pointer list-none p-5 hover:bg-slate-50 transition-colors">
                            <span>Can you provide customized retail packaging and barcodes?</span>
                            <span class="transition group-open:rotate-180">
                                <svg fill="none" height="24" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="24"><path d="M6 9l6 6 6-6"></path></svg>
                            </span>
                        </summary>
                        <div class="p-5 pt-0 text-slate-500 leading-relaxed border-t border-slate-100 mt-2 text-sm">
                            Absolutely. We can manufacture custom color boxes, display cartons, and apply UPC/EAN barcode stickers or print them directly on the packaging so products arrive ready for retail shelves.
                        </div>
                    </details>

                </div>
            </section>

        </div>
    </div>

</body>
</html>
```
