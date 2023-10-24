<script lang="ts">
// Import the functions you need from the SDKs you need
import { initializeApp } from "firebase/app";
import { getAnalytics } from "firebase/analytics";
// TODO: Add SDKs for Firebase products that you want to use
// https://firebase.google.com/docs/web/setup#available-libraries

// Your web app's Firebase configuration
// For Firebase JS SDK v7.20.0 and later, measurementId is optional
const firebaseConfig = {
  apiKey: "AIzaSyAgCMBPakhswTmlTKTKYVnKRobpe0j9Va0",
  authDomain: "eltd-e5693.firebaseapp.com",
  projectId: "eltd-e5693",
  storageBucket: "eltd-e5693.appspot.com",
  messagingSenderId: "323451723208",
  appId: "1:323451723208:web:ea7d0b9fa1062a7e8474fd",
  measurementId: "G-QTPKXK3XWQ"
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);
const analytics = getAnalytics(app);
export default app;
</script>