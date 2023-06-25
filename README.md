// Function to simulate an asynchronous API call
function fetchData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const success = Math.random() < 0.8; // 80% chance of success
      if (success) {
        resolve('Data retrieved successfully!');
      } else {
        reject(new Error('Failed to retrieve data.'));
      }
    }, 2000); // Simulating a delay of 2 seconds
  });
}

// Async function to handle the API call
async function handleAPICall() {
  try {
    console.log('Fetching data...');
    const result = await fetchData();
    console.log(result);
    console.log('Data handling complete.');
  } catch (error) {
    console.error('Error:', error.message);
  }
}

// Call the async function to initiate the API call handling
handleAPICall();
