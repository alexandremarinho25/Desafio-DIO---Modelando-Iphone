# Desafio-DIO---Modelando-Iphone
 Modelando o iPhone com UML: Funções de Músicas, Chamadas e Internet
// Device.java
public abstract class Device {
    protected String brand;
    protected String model;

    public void turnOn() {
        System.out.println("Device is turning on");
    }

    public void turnOff() {
        System.out.println("Device is turning off");
    }

    public void restart() {
        System.out.println("Device is restarting");
    }
}

// MusicPlayer.java
public interface MusicPlayer {
    void playTrack(String trackName);
    void pauseTrack();
    void stopTrack();
    void nextTrack();
    void previousTrack();
}

// Phone.java
public interface Phone {
    void makeCall(String phoneNumber);
    void receiveCall();
    void endCall();
    void sendTextMessage(String phoneNumber, String message);
    void receiveTextMessage();
}

// InternetBrowser.java
public interface InternetBrowser {
    void openWebsite(String url);
    void refreshPage();
    void goBack();
    void goForward();
    void addBookmark(String url);
    void removeBookmark(String url);
}

// iPhone.java
public class iPhone extends Device implements MusicPlayer, Phone, InternetBrowser {
    private String currentTrack;
    private String currentCall;
    private String currentWebsite;

    // Implementations of MusicPlayer methods
    public void playTrack(String trackName) {
        currentTrack = trackName;
        System.out.println("Playing track: " + trackName);
    }

    public void pauseTrack() {
        System.out.println("Pausing track: " + currentTrack);
    }

    public void stopTrack() {
        System.out.println("Stopping track: " + currentTrack);
        currentTrack = null;
    }

    public void nextTrack() {
        System.out.println("Skipping to next track");
    }

    public void previousTrack() {
        System.out.println("Returning to previous track");
    }

    // Implementations of Phone methods
    public void makeCall(String phoneNumber) {
        currentCall = phoneNumber;
        System.out.println("Calling: " + phoneNumber);
    }

    public void receiveCall() {
        System.out.println("Receiving a call");
    }

    public void endCall() {
        System.out.println("Ending the call with: " + currentCall);
        currentCall = null;
    }

    public void sendTextMessage(String phoneNumber, String message) {
        System.out.println("Sending message to " + phoneNumber + ": " + message);
    }

    public void receiveTextMessage() {
        System.out.println("Receiving a text message");
    }

    // Implementations of InternetBrowser methods
    public void openWebsite(String url) {
        currentWebsite = url;
        System.out.println("Opening website: " + url);
    }

    public void refreshPage() {
        System.out.println("Refreshing website: " + currentWebsite);
    }

    public void goBack() {
        System.out.println("Going back in browser history");
    }

    public void goForward() {
        System.out.println("Going forward in browser history");
    }

    public void addBookmark(String url) {
        System.out.println("Adding bookmark: " + url);
    }

    public void removeBookmark(String url) {
        System.out.println("Removing bookmark: " + url);
    }
    
    // Additional iPhone methods
    public void useFaceID() {
        System.out.println("Using Face ID");
    }

    public void takePhoto() {
        System.out.println("Taking a photo");
    }

    public void accessAppStore() {
        System.out.println("Accessing the App Store");
    }
}
