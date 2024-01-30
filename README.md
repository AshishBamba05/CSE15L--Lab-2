public class ChatServer {
    private static StringBuilder chatHistory = new StringBuilder();

    public static void main(String[] args) {
        get("/add-message", (req, res) -> {
            String message = req.queryParams("s");
            String user = req.queryParams("user");
            chatHistory.append(user).append(": ").append(message).append("\n");
            return chatHistory.toString();
        });
    }
}
