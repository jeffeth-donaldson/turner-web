<script lang="ts">
    import { FirebaseApp } from 'sveltefire';
    import { initializeApp } from 'firebase/app';
    import { getFirestore } from 'firebase/firestore';
    import { getAuth } from 'firebase/auth';

    // Initialize Firebase
    const app = initializeApp({
        apiKey: "AIzaSyDgM2J1WzeujSptvRK-lPEiOV-xxVK7NiI",
        authDomain: "turner-9bce1.firebaseapp.com",
        projectId: "turner-9bce1",
        storageBucket: "turner-9bce1.appspot.com",
        messagingSenderId: "749696450052",
        appId: "1:749696450052:web:8e462fcb4fc978a653bf51",
        measurementId: "G-M1NGV1SNPY"
    });
    const firestore = getFirestore(app);
    const auth = getAuth(app);
</script>

<FirebaseApp {auth} {firestore}>
    <slot />
</FirebaseApp>