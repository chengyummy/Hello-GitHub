# Hello-GitHub
这是我的第一个项目
package com.baidu.web.servlet;
import com.baidu.domain.Contact;
import com.baidu.service.ContactService;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;
import java.util.List;
@WebServlet("/showAll")
public class showAllServlet extends HttpServlet {
    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        doGet(request, response);
    }
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        ContactService contactService = new ContactService();
        List<Contact> contacts = contactService.showAll();
        System.out.println(contacts);
        request.setAttribute("list",contacts);
        request.getRequestDispatcher("list.jsp").forward(request,response);
    }
}

