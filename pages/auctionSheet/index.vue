<script setup>
import { ref, computed } from "vue";
import { Icon } from "@iconify/vue";

const search = ref("");
const activeTab = ref('all');

const auctionSheetTerms = {
  equipment: [
    { mark: 'AC', meaning: 'Air conditioner' },
    { mark: 'AAC', meaning: 'Climate control air conditioner' },
    { mark: 'PS', meaning: 'Power steering' },
    { mark: 'SR', meaning: 'Sunroof' },
    { mark: 'AW', meaning: 'Alloy wheels' },
    { mark: 'PW', meaning: 'Power windows' },
    { mark: 'TV', meaning: 'Television' },
    { mark: 'カワor ⾰', meaning: 'Leather seats' },
    { mark: 'AB or エアB', meaning: 'Airbag' }
  ],
  transmissions: [
    { mark: 'F6, 6MT or 6F', meaning: 'Manual (6-speed) transmission' },
    { mark: 'F5, 5MT or 5F', meaning: 'Manual (5-speed) transmission' },
    { mark: 'F4, 4MT or 4F', meaning: 'Manual (4-speed) transmission' },
    { mark: 'C4, 4CMT or 4C', meaning: 'Manual (4-speed) Column shift transmission' },
    { mark: 'D5, 5D', meaning: 'Manual (5-speed) Dashboard-mounted transmission' },
    { mark: 'I5, 5I', meaning: 'Manual (5-speed) Instrument panel shift transmission' },
    { mark: 'CA or CAT', meaning: 'Column Automatic transmission' },
    { mark: 'FAT/AT', meaning: 'Floor Automatic transmission' },
    { mark: '5FAT', meaning: '5-speed Floor Automatic transmission' },
    { mark: '6FAT', meaning: '6-speed Floor Automatic transmission' },
    { mark: 'DAT', meaning: 'Dashboard-mounted automatic transmission' },
    { mark: '5DAT', meaning: '5-speed Dashboard-mounted automatic transmission' },
    { mark: 'IAT', meaning: 'Instrument panel shift automatic transmission' },
    { mark: '5IAT', meaning: '5-speed Instrument panel shift Automatic transmission' }
  ],
  odometer: [
    { mark: '*', meaning: 'Odometer clocked or re-wound' },
    { mark: '＄', meaning: 'Speedometer replacement made with proof of mileage' },
    { mark: '#', meaning: 'Unknown mileage' }
  ],
  defects: [
    { mark: 'A', degree: '1,2,3,4', meaning: 'Line scratch' },
    { mark: 'U', degree: '1,2,3,4', meaning: 'Dent' },
    { mark: 'B', degree: '1,2,3,4', meaning: 'Dent with scratches (requiring panel beating and respray )' },
    { mark: 'P', degree: '1,2,3,4', meaning: 'Painting required, paint peeling, fading' },
    { mark: 'W', degree: '1,2,3', meaning: 'Repair waves or traces' },
    { mark: 'S', degree: '1,2,3,4', meaning: 'Rust' },
    { mark: 'C', degree: '1,2,3,4', meaning: 'Corrosion' },
    { mark: 'X', degree: 'Occasionally 1,2,3 depending on the auction house', meaning: 'Replacement required' },
    { mark: 'XX', degree: 'None', meaning: 'Panel replaced' },
    { mark: 'Y', degree: '1,2,3', meaning: 'Cracks or tears mainly on bumpers or side skirts etc' },
    { mark: 'E', degree: 'None or 1,2,3 depending on the auction houses', meaning: 'Tiny dent' },
    { mark: 'x (small)', degree: 'Used in some auctions', meaning: 'Small crack on windshield screen' },
    { mark: 'D', degree: '1,2,3, T⼤、T多 Used in a few auctions', meaning: 'Crack' },
    { mark: 'F', degree: '1,2,3 Used in a few auctions', meaning: 'Paint peeling off' },
    { mark: 'T', degree: '1,2,3, T⼤、T多 Used in a few auctions', meaning: 'Cut' },
    { mark: 'G', degree: 'Used in some auctions', meaning: 'Chip or Dots on windshield screen' },
    { mark: 'H', degree: '1,2,3 Used in a few auctions', meaning: 'Discolor or Fade' },
    { mark: 'L', degree: 'Used in a few auctions', meaning: 'Shifted' },
    { mark: 'O', degree: 'Used in a few auctions', meaning: 'Pushed in' },
    { mark: 'BP', degree: 'Used in inspectors comments', meaning: 'Repaired trace or dent with paint blemish' }
  ]
};

const sampleFindings = [
  { code: 'A1', location: 'right side of the front bumper', interpretation: "There are some minor scratches, since it's marked as 1." },
  { code: 'B2', location: 'left side of the front bumper', interpretation: "There is a dent with scratches. Mark 2 indicates they're more visible, probably the size of the palm." },
  { code: 'B1', location: 'left front wing (fender)', interpretation: 'There is a small dent with scratches.' },
  { code: 'A1', location: 'left front wing (fender)', interpretation: 'There are small scratches.' },
  { code: 'A1', location: 'left sliding door', interpretation: 'There are small scratches.' }
];

const auctionGrades = [
  { mark: 'S', meaning: 'The car is less than a year old from the date of first registration and has travelled less than 10,000 km. The car is in perfect condition, as good as factory new.' },
  { mark: '6', meaning: 'The car is in perfect condition almost as new, less than three years old from the first registration date and the mileage less than 30,000km.' },
  { mark: '5', meaning: 'The car has mileage less than 50,000 km. There may be some minor scratches and marks on the body. There may be some interior stains, stains, glue marks, burns, breaks, etc.' },
  { mark: '4.5', meaning: 'The car has mileage less than 100,000 km. There are more minor scratches and marks on the body than Grade 5. It is equivalent to Grade 5 with minor repairs. There are several flaws on the exterior. The interior has some scorching holes, cracks, rubbing, discoloration, fading, etc.' },
  { mark: '4', meaning: 'The car mileage is less than 150,000km. The car has several noticeable scratches and minor dents on its body. There are noticeable interior defects which may require repair.' },
  { mark: '3.5', meaning: 'The exterior may have a few mid or large size dents and scratches that require repair or replacement. There may be noticeable interior defects which may need replacement. The car may have done outer welding panel replacement of the main panel.' },
  { mark: '3', meaning: 'Both the interior and exterior may have some large dents scuffs or scratches that require repair or replacement. There may be major mechanical defects.' },
  { mark: '2', meaning: 'Those with low commercial value.' },
  { mark: '1', meaning: 'Disaster vehicle (submerged vehicle, extinguisher spray vehicle, etc.)' },
  { mark: '0', meaning: 'Accident repaired car or accident unrepaired car' },
  { mark: 'R', meaning: 'Accident repaired car' },
  { mark: 'RA', meaning: 'Light accident repaired car' },
  { mark: '***', meaning: 'Accident car or Engine may not work' }
];

const interiorGrades = [
  { grade: 'A', condition: 'Mileage is within 30,000km There are slight flaws. It may have some stains, scratches, glue, etc' },
  { grade: 'B', condition: 'There are several minor defects. It may have cigarette burns, cuts, or tears' },
  { grade: 'C', condition: 'There are several defects that require minor repairs. It has some cuts, tears, charred holes, glue marks, glue, etc.' },
  { grade: 'D', condition: 'There are several conspicuous defects that require repairs' },
  { grade: 'E', condition: 'It is obviously in bad condition. It requires replacement of major parts such as dashboards, headliner, seats, etc.' },
  { grade: 'F', condition: "It is below Grade E's interior condition." }
];

const exteriorGrades = [
  { grade: 'A', condition: 'It is close to new with slight flaws. It might have a slight repair trace' },
  { grade: 'B', condition: 'There are conspicuous flaws. Windshields and lights might be with small cracks. There may be a large flaw on bumpers, glasses, hoods and screens' },
  { grade: 'C', condition: 'There are several conspicuous defects. It may have a noticeable dent. It has repair marks that require re-repairing' },
  { grade: 'D', condition: 'It has some defects that require repairs. It has noticeable corrosion' },
  { grade: 'E', condition: 'It has many defects that require repairs. It may be with a lot of corrosion' },
  { grade: 'F', condition: "It is below Grade E's exterior condition" }
];

const translationTerms = [
  { code: 'A1', description: 'Small Scratch' },
  { code: 'A2', description: 'Scratch' },
  { code: 'A3', description: 'Big Scratch' },
  { code: 'E1', description: 'Few Dimples' },
  { code: 'E2', description: 'Several Dimples' },
  { code: 'E3', description: 'Many Dimples' },
  { code: 'U1', description: 'Small Dent' },
  { code: 'U2', description: 'Dent' },
  { code: 'U3', description: 'Big Dent' },
  { code: 'W1', description: 'Repair Mark/Wave (hardly detectable)' },
  { code: 'W2', description: 'Repair Mark/Wave' },
  { code: 'W3', description: 'Obvious Repair Mark/Wave (needs to be repainted)' },
  { code: 'S1', description: 'Rust' },
  { code: 'S2', description: 'Heavy Rust' },
  { code: 'C1', description: 'Corrosion' },
  { code: 'C2', description: 'Heavy Corrosion' },
  { code: 'P', description: 'Paint marked' },
  { code: 'H', description: 'Paint faded' },
  { code: 'X', description: 'Need to be replaced' },
  { code: 'X', description: 'Replaced' },
  { code: 'B1', description: 'Small Dent with scratch' },
  { code: 'B2', description: 'Dent with scratch (like flat of the hand)' },
  { code: 'B3', description: 'Big Dent with scratch (like elbow)' },
  { code: 'Y1', description: 'Small Hole or Crack' },
  { code: 'Y2', description: 'Hole or Crack' },
  { code: 'Y3', description: 'Big Hole or Crack' },
  { code: 'X1', description: 'Small Crack on Windshield (approx. 1cm)' },
  { code: 'R', description: 'Repaired Crack on Windshield' },
  { code: 'RX', description: 'Replaced Crack on Windshield (needs to be replaced)' },
  { code: 'XX', description: 'Crack on Windshield (needs to be replaced)' },
  { code: 'G', description: 'Stone chip in glass' }
];

const filteredEquipment = computed(() => {
  if (!search.value) return auctionSheetTerms.equipment;
  return auctionSheetTerms.equipment.filter(item => 
    item.mark.toLowerCase().includes(search.value.toLowerCase()) || 
    item.meaning.toLowerCase().includes(search.value.toLowerCase())
  );
});

const filteredTransmissions = computed(() => {
  if (!search.value) return auctionSheetTerms.transmissions;
  return auctionSheetTerms.transmissions.filter(item => 
    item.mark.toLowerCase().includes(search.value.toLowerCase()) || 
    item.meaning.toLowerCase().includes(search.value.toLowerCase())
  );
});

const filteredOdometer = computed(() => {
  if (!search.value) return auctionSheetTerms.odometer;
  return auctionSheetTerms.odometer.filter(item => 
    item.mark.toLowerCase().includes(search.value.toLowerCase()) || 
    item.meaning.toLowerCase().includes(search.value.toLowerCase())
  );
});

const filteredDefects = computed(() => {
  if (!search.value) return auctionSheetTerms.defects;
  return auctionSheetTerms.defects.filter(item => 
    item.mark.toLowerCase().includes(search.value.toLowerCase()) || 
    item.meaning.toLowerCase().includes(search.value.toLowerCase()) ||
    item.degree.toLowerCase().includes(search.value.toLowerCase())
  );
});

const filteredAuctionGrades = computed(() => {
  if (!search.value) return auctionGrades;
  return auctionGrades.filter(item => 
    item.mark.toLowerCase().includes(search.value.toLowerCase()) || 
    item.meaning.toLowerCase().includes(search.value.toLowerCase())
  );
});

const filteredInteriorGrades = computed(() => {
  if (!search.value) return interiorGrades;
  return interiorGrades.filter(item => 
    item.grade.toLowerCase().includes(search.value.toLowerCase()) || 
    item.condition.toLowerCase().includes(search.value.toLowerCase())
  );
});

const filteredExteriorGrades = computed(() => {
  if (!search.value) return exteriorGrades;
  return exteriorGrades.filter(item => 
    item.grade.toLowerCase().includes(search.value.toLowerCase()) || 
    item.condition.toLowerCase().includes(search.value.toLowerCase())
  );
});

const filteredTranslationTerms = computed(() => {
  if (!search.value) return translationTerms;
  return translationTerms.filter(item => 
    item.code.toLowerCase().includes(search.value.toLowerCase()) || 
    item.description.toLowerCase().includes(search.value.toLowerCase())
  );
});

const filteredSampleFindings = computed(() => {
  if (!search.value) return sampleFindings;
  return sampleFindings.filter(item => 
    item.code.toLowerCase().includes(search.value.toLowerCase()) || 
    item.location.toLowerCase().includes(search.value.toLowerCase()) ||
    item.interpretation.toLowerCase().includes(search.value.toLowerCase())
  );
});
</script>

<template>
  <section class="w-full relative overflow-hidden bg-gradient-to-br from-slate-50 via-white to-slate-100">
    <div class="absolute top-0 right-0 w-96 h-96 bg-primary/10 rounded-full -translate-y-1/3 translate-x-1/3 blur-3xl animate-pulse-slow"></div>
    <div class="absolute bottom-0 left-0 w-[32rem] h-[32rem] bg-secondary/10 rounded-full translate-y-1/3 -translate-x-1/3 blur-3xl animate-pulse-slow delay-1000"></div>
    <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-primary/5 rounded-full blur-3xl animate-pulse-slow delay-500"></div>
    <div class="absolute inset-0 opacity-[0.03] bg-grid-pattern"></div>

    <div class="container mx-auto px-4 relative">
      <div class="text-center mb-8">
        <h1 class="text-4xl md:text-5xl font-bold text-gray-800 mb-4">Car Auction Sheet Guide</h1>
        <p class="text-lg text-gray-600 max-w-3xl mx-auto">A comprehensive guide to understanding  auction sheets for used vehicles</p>
      </div>
      <div class="w-full h-full my-8">
        <img src="/images/carDetails.png" alt="Auction Sheet Diagram" class="mx-auto object-contain max-h-[650px] w-[600px]" />
      </div>
    </div>

    <div class="w-full relative overflow-hidden py-6 md:py-10">
      <div class="container mx-auto px-4 relative">
        <div class="bg-white shadow-xl rounded-xl p-6 border border-gray-200 mb-10">
          <h3 class="text-2xl font-bold text-gray-800 mb-6 pb-2 border-b border-gray-200">
            Understanding the Auction Sheet
          </h3>
          
          <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <div>
              <h4 class="text-lg font-semibold text-gray-700 mb-4">Common Defect Codes</h4>
              <div class="bg-gray-50 rounded-lg p-4 max-h-[500px] overflow-y-auto">
                <table class="min-w-full divide-y divide-gray-200">
                  <thead class="bg-gray-100 sticky top-0">
                    <tr>
                      <th class="px-4 py-2 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Code</th>
                      <th class="px-4 py-2 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Description</th>
                    </tr>
                  </thead>
                  <tbody class="bg-white divide-y divide-gray-200">
                    <tr v-for="(term, index) in filteredTranslationTerms" :key="index" class="hover:bg-gray-50">
                      <td class="px-4 py-3 whitespace-nowrap text-sm font-medium text-gray-900">{{ term.code }}</td>
                      <td class="px-4 py-3 text-sm text-gray-600">{{ term.description }}</td>
                    </tr>
                  </tbody>
                </table>
              </div>
            </div>

            <div>
              <h4 class="text-lg font-semibold text-gray-700 mb-4">Grade Information</h4>
              <div class="bg-blue-50 rounded-lg p-4 mb-4">
                <p class="text-gray-700"><strong>Example:</strong> Rate ext: C, Rate int: B</p>
                <p class="text-gray-600 text-sm mt-1">This indicates the exterior grade is C and interior grade is B</p>
              </div>
              
              <div class="bg-yellow-50 rounded-lg p-4">
                <h5 class="font-medium text-gray-700 mb-2">Quick Reference</h5>
                <ul class="space-y-1 text-sm text-gray-600">
                  <li><span class="font-medium">S Grade:</span> Like new, less than 1 year old</li>
                  <li><span class="font-medium">6-5 Grade:</span> Excellent condition with minor flaws</li>
                  <li><span class="font-medium">4-3 Grade:</span> Good condition with noticeable defects</li>
                  <li><span class="font-medium">R/RA Grade:</span> Accident history (repaired)</li>
                  <li><span class="font-medium">0/1 Grade:</span> Accident history or disaster damage</li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="container mx-auto px-4">
      <div class="mb-10">
        <h2 class="text-3xl font-bold text-gray-800 mb-4">WHAT IS AN AUCTION SHEET?</h2>
        <div class="bg-transparent mb-6">
          <p class="text-gray-600 mb-4">
            Auction sheets are often the first point of inspection when considering to purchase a used car. They are made by professional inspectors and offer a good overview of the vehicle's condition, history and basic information.
          </p>
          <p class="text-gray-600">
            Auction sheets have different formats, and are written in . Please refer to the sample Auction Sheet above with English translations, for your reference.
          </p>
        </div>
      </div>

      <div class="mb-10">
        <h2 class="text-3xl font-bold text-gray-800 mb-4">Auction Sheet Terms</h2>
        <p class="text-gray-600 mb-6 max-w-3xl">
          Auction Sheets make use of certain terms to describe vehicle parts and/or defects. Please see the list of common terms used in Auction sheets.
        </p>

        <div class="space-y-8">
          <div>
            <h3 class="text-xl font-semibold text-gray-700 mb-4 flex items-center">
              <Icon icon="mdi:car-settings" class="mr-2 text-primary" />
              Equipment/ Accessories
            </h3>
            <div class="overflow-x-auto bg-white rounded-xl shadow-lg">
              <table class="min-w-full divide-y divide-gray-200">
                <thead class="bg-gray-50">
                  <tr>
                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Mark</th>
                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Meaning</th>
                  </tr>
                </thead>
                <tbody class="bg-white divide-y divide-gray-200">
                  <tr v-for="(item, index) in filteredEquipment" :key="index" class="hover:bg-gray-50">
                    <td class="px-4 py-4 whitespace-nowrap text-sm font-medium text-gray-900">{{ item.mark }}</td>
                    <td class="px-4 py-4 whitespace-normal text-sm text-gray-600">{{ item.meaning }}</td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>

          <div>
            <h3 class="text-xl font-semibold text-gray-700 mb-4 flex items-center">
              <Icon icon="mdi:car-shift-pattern" class="mr-2 text-primary" />
              Transmissions
            </h3>
            <div class="overflow-x-auto bg-white rounded-xl shadow-lg">
              <table class="min-w-full divide-y divide-gray-200">
                <thead class="bg-gray-50">
                  <tr>
                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Mark</th>
                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Meaning</th>
                  </tr>
                </thead>
                <tbody class="bg-white divide-y divide-gray-200">
                  <tr v-for="(item, index) in filteredTransmissions" :key="index" class="hover:bg-gray-50">
                    <td class="px-4 py-4 whitespace-nowrap text-sm font-medium text-gray-900">{{ item.mark }}</td>
                    <td class="px-4 py-4 whitespace-normal text-sm text-gray-600">{{ item.meaning }}</td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>

          <div>
            <h3 class="text-xl font-semibold text-gray-700 mb-4 flex items-center">
              <Icon icon="mdi:speedometer" class="mr-2 text-primary" />
              Odometer Reading Authenticity
            </h3>
            <div class="overflow-x-auto bg-white rounded-xl shadow-lg">
              <table class="min-w-full divide-y divide-gray-200">
                <thead class="bg-gray-50">
                  <tr>
                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Mark</th>
                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Meaning</th>
                  </tr>
                </thead>
                <tbody class="bg-white divide-y divide-gray-200">
                  <tr v-for="(item, index) in filteredOdometer" :key="index" class="hover:bg-gray-50">
                    <td class="px-4 py-4 whitespace-nowrap text-sm font-medium text-gray-900">{{ item.mark }}</td>
                    <td class="px-4 py-4 whitespace-normal text-sm text-gray-600">{{ item.meaning }}</td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>

          <div>
            <h3 class="text-xl font-semibold text-gray-700 mb-4 flex items-center">
              <Icon icon="mdi:car-wrench" class="mr-2 text-primary" />
              Vehicle Defects
            </h3>
            <div class="overflow-x-auto bg-white rounded-xl shadow-lg">
              <table class="min-w-full divide-y divide-gray-200">
                <thead class="bg-gray-50">
                  <tr>
                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Mark</th>
                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Degree of Condition / Notes</th>
                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Meaning</th>
                  </tr>
                </thead>
                <tbody class="bg-white divide-y divide-gray-200">
                  <tr v-for="(item, index) in filteredDefects" :key="index" class="hover:bg-gray-50">
                    <td class="px-4 py-4 whitespace-nowrap text-sm font-medium text-gray-900">{{ item.mark }}</td>
                    <td class="px-4 py-4 whitespace-normal text-sm text-gray-600">{{ item.degree }}</td>
                    <td class="px-4 py-4 whitespace-normal text-sm text-gray-600">{{ item.meaning }}</td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>

      <div class="mb-10">
        <h2 class="text-3xl font-bold text-gray-800 mb-4">Sample Findings</h2>
        <p class="text-gray-600 mb-6 max-w-3xl">
          Terms inside the yellow frame describe the condition of the vehicle's parts. You may refer to the "Vehicle Defects" table above for details about marks and their meaning. In this sample Auction Sheet, we can find the following:
        </p>
        
        <div class="bg-white rounded-xl shadow-lg p-6">
          <ul class="space-y-4">
            <li v-for="(f, idx) in filteredSampleFindings" :key="idx" class="border-l-4 border-primary pl-4 py-1">
              <div class="flex flex-col md:flex-row md:items-center">
                <span class="font-bold text-lg text-gray-800 mr-3">[{{ f.code }}]</span>
                <span class="text-gray-700 italic">{{ f.location }}</span>
              </div>
              <p class="text-gray-600 mt-1">Interpretation: {{ f.interpretation }}</p>
            </li>
          </ul>
        </div>
      </div>

      <div class="mb-10">
        <h2 class="text-3xl font-bold text-gray-800 mb-4">WHAT IS AN AUCTION GRADE?</h2>
        <p class="text-gray-600 mb-8 max-w-3xl">
          A vehicle is graded primarily on the basis of its mileage, interior, and exterior condition. The auction grade helps you evaluate the condition of the vehicle. Please refer to the following tables for Auction Grade interpretations.
        </p>

        <div class="space-y-8">
          <div>
            <h3 class="text-xl font-semibold text-gray-700 mb-4 flex items-center">
              <Icon icon="mdi:star-circle" class="mr-2 text-primary" />
              Auction Grade
            </h3>
            <div class="overflow-x-auto bg-white rounded-xl shadow-lg">
              <table class="min-w-full divide-y divide-gray-200">
                <thead class="bg-gray-50">
                  <tr>
                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Mark</th>
                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Meaning</th>
                  </tr>
                </thead>
                <tbody class="bg-white divide-y divide-gray-200">
                  <tr v-for="(item, index) in filteredAuctionGrades" :key="index" class="hover:bg-gray-50">
                    <td class="px-4 py-4 whitespace-nowrap text-sm font-medium text-gray-900">{{ item.mark }}</td>
                    <td class="px-4 py-4 whitespace-normal text-sm text-gray-600">{{ item.meaning }}</td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>

          <div>
            <h3 class="text-xl font-semibold text-gray-700 mb-4 flex items-center">
              <Icon icon="mdi:car-seat" class="mr-2 text-primary" />
              Interior Grade
            </h3>
            <div class="overflow-x-auto bg-white rounded-xl shadow-lg">
              <table class="min-w-full divide-y divide-gray-200">
                <thead class="bg-gray-50">
                  <tr>
                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Grade</th>
                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Vehicle Condition</th>
                  </tr>
                </thead>
                <tbody class="bg-white divide-y divide-gray-200">
                  <tr v-for="(item, index) in filteredInteriorGrades" :key="index" class="hover:bg-gray-50">
                    <td class="px-4 py-4 whitespace-nowrap text-sm font-medium text-gray-900">{{ item.grade }}</td>
                    <td class="px-4 py-4 whitespace-normal text-sm text-gray-600">{{ item.condition }}</td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>

          <div>
            <h3 class="text-xl font-semibold text-gray-700 mb-4 flex items-center">
              <Icon icon="mdi:car-door" class="mr-2 text-primary" />
              Exterior Grade
            </h3>
            <div class="overflow-x-auto bg-white rounded-xl shadow-lg">
              <table class="min-w-full divide-y divide-gray-200">
                <thead class="bg-gray-50">
                  <tr>
                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Grade</th>
                    <th class="px-4 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Vehicle Condition</th>
                  </tr>
                </thead>
                <tbody class="bg-white divide-y divide-gray-200">
                  <tr v-for="(item, index) in filteredExteriorGrades" :key="index" class="hover:bg-gray-50">
                    <td class="px-4 py-4 whitespace-nowrap text-sm font-medium text-gray-900">{{ item.grade }}</td>
                    <td class="px-4 py-4 whitespace-normal text-sm text-gray-600">{{ item.condition }}</td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style>
@keyframes pulse-slow {
  0%, 100% { opacity: 0.5; }
  50% { opacity: 0.8; }
}

.animate-pulse-slow {
  animation: pulse-slow 4s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

.bg-grid-pattern {
  background-image: linear-gradient(rgba(0, 0, 0, 0.05) 1px, transparent 1px),
                    linear-gradient(90deg, rgba(0, 0, 0, 0.05) 1px, transparent 1px);
  background-size: 20px 20px;
}

/* Custom scrollbar for tables */
.overflow-y-auto::-webkit-scrollbar {
  width: 6px;
}

.overflow-y-auto::-webkit-scrollbar-track {
  background: #f1f1f1;
  border-radius: 10px;
}

.overflow-y-auto::-webkit-scrollbar-thumb {
  background: #888;
  border-radius: 10px;
}

.overflow-y-auto::-webkit-scrollbar-thumb:hover {
  background: #555;
}
</style>