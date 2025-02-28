import cv2
import face_recognition

def load_and_encodes(image_path):
    # Load the image
    image = face_recognition.load_image_file(image_path)
    # Get the face encodings for any faces in the image
    encodings = face_recognition.face_encodings(image)
    if len(encodings) > 0:
        return encodings[0]
    else:
        return None

def compare_faces(stored_image_path, given_image_path):
    # Load and encode the stored image
    stored_encoding = load_and_encodes(stored_image_path)
    if stored_encoding is None:
        print("No face found in the stored image.")
        return

    # Load and encode the given image
    given_encoding = load_and_encodes(given_image_path)
    if given_encoding is None:
        print("No face found in the given image.")
        return

    # Compare faces
    results = face_recognition.compare_faces([stored_encoding], given_encoding)
    if results[0]:
        print("The faces match!")
    else:
        print("The faces do not match.")

if __name__ == "__main__":
    stored_image_path = 'path_to_stored_image.jpg'
    given_image_path = 'path_to_given_image.jpg'
    compare_faces(stored_image_path, given_image_path)
