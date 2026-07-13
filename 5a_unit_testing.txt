import unittest
from EmotionDetection import emotion_detector


class TestEmotionDetector(unittest.TestCase):

    def test_emotion_detector(self):

        result = emotion_detector("I am glad this happened")
        self.assertEqual(result["dominant_emotion"], "joy")

        result = emotion_detector("I am really angry about this")
        self.assertEqual(result["dominant_emotion"], "anger")

        result = emotion_detector("I am disgusted just hearing this")
        self.assertEqual(result["dominant_emotion"], "disgust")

        result = emotion_detector("I am very sad about this")
        self.assertEqual(result["dominant_emotion"], "sadness")

        result = emotion_detector("I am really afraid that this will happen")
        self.assertEqual(result["dominant_emotion"], "fear")


if __name__ == "__main__":
    unittest.main()
