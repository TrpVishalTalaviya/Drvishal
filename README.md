import UIKit

class ViewController: UIViewController {

    @IBOutlet weak var textView: UITextView!

    override func viewDidLoad() {
        super.viewDidLoad()
    }

    @IBAction func copyText(_ sender: Any) {
        UIPasteboard.general.string = textView.text
    }

    @IBAction func cutText(_ sender: Any) {
        UIPasteboard.general.string = textView.text
        textView.text = ""
    }

    @IBAction func pasteText(_ sender: Any) {
        if let copiedText = UIPasteboard.general.string {
            textView.text += copiedText
        }
    }
}
